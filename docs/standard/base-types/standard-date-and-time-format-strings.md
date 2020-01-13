---
title: Standardformatzeichenfolgen für Datum und Uhrzeit
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- formatting [.NET Framework], dates
- custom DateTime format string
- format specifiers, custom date and time
- format strings
- custom date and time format strings
- formatting [.NET Framework], time
- date and time strings
ms.assetid: bb79761a-ca08-44ee-b142-b06b3e2fc22b
ms.openlocfilehash: 883902142a91e275ab64ad5d12c197c665bd9b36
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346651"
---
# <a name="standard-date-and-time-format-strings"></a>Standardformatzeichenfolgen für Datum und Uhrzeit

Eine standardmäßige Formatzeichenfolge für Datum und Uhrzeit verwendet einen einzelnen Formatbezeichner, um die Textdarstellung eines Datums- und Uhrzeitwerts zu definieren. Jede Formatzeichenfolge für Datum und Uhrzeit, die mehr als ein Zeichen (einschließlich Leerzeichen) enthält, wird als benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit interpretiert. Weitere Informationen finden Sie unter [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](../../../docs/standard/base-types/custom-date-and-time-format-strings.md). Eine standardmäßige oder benutzerdefinierte Formatzeichenfolge kann auf zwei Arten verwendet werden:

- Zum Definieren der Zeichenfolge, die das Ergebnis eines Formatierungsvorgangs ist.

- Zum Definieren der Textdarstellung eines Datums- und Uhrzeitwerts, der bei einem Analysevorgang in einen <xref:System.DateTime>-Wert oder in einen <xref:System.DateTimeOffset>-Wert konvertiert werden kann.

> [!TIP]
> Sie können das **Hilfsprogramm zur Formatierung** herunterladen. Dabei handelt sich um eine Windows Forms-Anwendung für .NET Core, mit der Sie Formatzeichenfolgen auf numerische Werte oder Datums- und Zeitwerte anwenden und die Ergebniszeichenfolge anzeigen können. Für [C#](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs) und [Visual Basic](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-vb) ist Quellcode verfügbar.

Standard-Formatzeichenfolgen für Datum und Uhrzeit können mit dem Wert <xref:System.DateTime> und mit dem Wert <xref:System.DateTimeOffset> verwendet werden.

[!INCLUDE[C# interactive-note](~/includes/csharp-interactive-with-utc-partial-note.md)]

<a name="table"></a> In der folgenden Tabelle werden die Standardformatbezeichner für Datum und Uhrzeit beschrieben. Sofern nicht anders angegeben, erzeugt ein bestimmter Standardformatbezeichner für Datum und Uhrzeit eine identische Zeichenfolgendarstellung, unabhängig davon, ob sie mit einem <xref:System.DateTime>-Wert oder einem <xref:System.DateTimeOffset>-Wert verwendet wird. Weitere Informationen zum Verwenden von standardmäßigen Formatzeichenfolgen für Datum und Uhrzeit finden Sie im Abschnitt [Hinweise](#Notes).

|Formatbezeichner|Beschreibung|Beispiele|
|----------------------|-----------------|--------------|
|"d"|Kurzes Datumsmuster.<br /><br /> Weitere Informationen finden Sie unter [Der Formatbezeichner "d" für das kurze Datum](#ShortDate).|2009-06-15T13:45:30 -> 6/15/2009 (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15/06/2009 (fr-FR)<br /><br /> 2009-06-15T13:45:30 -> 2009/06/15 (ja-JP)|
|"D"|Langes Datumsmuster.<br /><br /> Weitere Informationen finden Sie unter [Der Formatbezeichner "D" für das lange Datum](#LongDate).|2009-06-15T13:45:30 -> Monday, June 15, 2009 (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15 июня 2009 г. (ru-RU)<br /><br /> 2009-06-15T13:45:30 -> Montag, 15. Juni 2009 (de-DE)|
|"f"|Vollständiges Datums-/Zeitmuster (kurze Zeit).<br /><br /> Weitere Informationen finden Sie unter: [Der Formatspezifizierer „f“ für vollständiges Datum und kurze Zeit](#FullDateShortTime).|2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> den 15 juni 2009 13:45 (sv-SE)<br /><br /> 2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45 μμ (el-GR)|
|"F"|Vollständiges Datums-/Zeitmuster (lange Zeit).<br /><br /> Weitere Informationen finden Sie unter: [Der Formatspezifizierer „F“ für vollständiges Datum und lange Zeit](#FullDateLongTime).|2009-06-15T13:45:30 -> Monday, June 15, 2009 1:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> den 15 juni 2009 13:45:30 (sv-SE)<br /><br /> 2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 1:45:30 μμ (el-GR)|
|"g"|Allgemeines Datums-/Zeitmuster (kurze Zeit).<br /><br /> Weitere Informationen finden Sie unter: [Der allgemeine Formatspezifizierer „g“ für Datum und kurze Zeit](#GeneralDateShortTime).|2009-06-15T13:45:30 -> 6/15/2009 1:45 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15/06/2009 13:45 (es-ES)<br /><br /> 2009-06-15T13:45:30 -> 2009/6/15 13:45 (zh-CN)|
|"G"|Allgemeines Datums-/Zeitmuster (lange Zeit).<br /><br /> Weitere Informationen finden Sie unter: [Der allgemeine Formatspezifizierer „G“ für Datum und lange Zeit](#GeneralDateLongTime).|2009-06-15T13:45:30 -> 6/15/2009 1:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15/06/2009 13:45:30 (es-ES)<br /><br /> 2009-06-15T13:45:30 -> 2009/6/15 13:45:30 (zh-CN)|
|"M", "m"|Monatstagmuster.<br /><br /> Weitere Informationen finden Sie unter: [Der Formatspezifizierer „M“, „m“ für den Monat](#MonthDay).|2009-06-15T13:45:30 -> June 15 (en-US)<br /><br /> 2009-06-15T13:45:30 -> 15. juni (da-DK)<br /><br /> 2009-06-15T13:45:30 -> 15 Juni (id-ID)|
|"O", "o"|Zurückkonvertieren von Datums-/Zeitmuster.<br /><br /> Weitere Informationen finden Sie unter: [Der Formatspezifizierer „O“, „o“ für Roundtrips](#Roundtrip).|<xref:System.DateTime>-Werte sind:<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Local) --> 2009-06-15T13:45:30.0000000-07:00<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Utc) --> 2009-06-15T13:45:30.0000000Z<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Unspecified) --> 2009-06-15T13:45:30.0000000<br /><br /> <xref:System.DateTimeOffset>:<br /><br /> 2009-06-15T13:45:30-07:00 --> 2009-06-15T13:45:30.0000000-07:00|
|"R", "r"|RFC1123-Muster.<br /><br /> Weitere Informationen finden Sie unter: [Der RFC1123-Formatspezifizierer „R“, „r“](#RFC1123).|2009-06-15T13:45:30 -> Mon, 15 Jun 2009 20:45:30 GMT|
|"s"|Sortierbares Datums-/Zeitmuster.<br /><br /> Weitere Informationen finden Sie unter: [Der sortierbare Formatspezifizierer „s“](#Sortable).|2009-06-15T13:45:30 (DateTimeKind.Local) -> 2009-06-15T13:45:30<br /><br /> 2009-06-15T13:45:30 (DateTimeKind.Utc) -> 2009-06-15T13:45:30|
|"t"|Kurzes Zeitmuster.<br /><br /> Weitere Informationen finden Sie unter: [Der Formatspezifizierer „t“ für kurze Zeit](#ShortTime).|2009-06-15T13:45:30 -> 1:45 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 13:45 (hr-HR)<br /><br /> 2009-06-15T13:45:30 -> 01:45 م (ar-EG)|
|"T"|Langes Zeitmuster.<br /><br /> Weitere Informationen finden Sie unter: [Der Formatspezifizierer „T“ für lange Zeit](#LongTime).|2009-06-15T13:45:30 -> 1:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> 13:45:30 (hr-HR)<br /><br /> 2009-06-15T13:45:30 -> 01:45:30 م (ar-EG)|
|"u"|Universelles, sortierbares Datums-/Zeitmuster.<br /><br /> Weitere Informationen finden Sie unter: [Der universelle sortierbare Formatspezifizierer „u“](#UniversalSortable).|Mit einem <xref:System.DateTime>-Wert: 2009-06-15T13:45:30 -> 2009-06-15 13:45:30Z<br /><br /> Mit einem <xref:System.DateTimeOffset>-Wert: 2009-06-15T13:45:30 -> 2009-06-15 20:45:30Z|
|"U"|Universelles Datums-/Zeitmuster (Koordinierte Weltzeit).<br /><br /> Weitere Informationen finden Sie unter: [Der universelle vollständige Formatspezifizierer „U“](#UniversalFull).|2009-06-15T13:45:30 -> Monday, June 15, 2009 8:45:30 PM (en-US)<br /><br /> 2009-06-15T13:45:30 -> den 15 juni 2009 20:45:30 (sv-SE)<br /><br /> 2009-06-15T13:45:30 -> Δευτέρα, 15 Ιουνίου 2009 8:45:30 μμ (el-GR)|
|"Y", "y"|Jahr-Monat-Muster.<br /><br /> Weitere Informationen finden Sie unter: [Der Formatspezifizierer „Y“, „y“ für Jahr-Monat](#YearMonth).|2009-06-15T13:45:30 -> June, 2009 (en-US)<br /><br /> 2009-06-15T13:45:30 -> juni 2009 (da-DK)<br /><br /> 2009-06-15T13:45:30 -> Juni 2009 (id-ID)|
|Jedes andere einzelne Zeichen|Unbekannter Bezeichner.|Löst eine <xref:System.FormatException> zur Laufzeit aus.|

## <a name="how-standard-format-strings-work"></a>Funktionsweise der Standardformatzeichenfolgen

Bei einem Formatierungsvorgang ist eine Standardformatzeichenfolge lediglich ein Alias für eine benutzerdefinierte Formatzeichenfolge. Die Verwendung eines Alias, der auf eine benutzerdefinierte Formatzeichenfolge verweist, hat den Vorteil, dass der Alias unveränderlich bleibt, während die benutzerdefinierte Formatzeichenfolge selbst variieren kann. Dies ist wichtig, da sich die Zeichenfolgenentsprechungen von Datums- und Uhrzeitwerten i. d. R. abhängig von der Kultur unterscheiden. So gibt beispielsweise die Standardformatzeichenfolge "d" an, dass der Datums- und Uhrzeitwert in einem kurzen Datumsmuster angezeigt wird. Für die invariante Kultur lautet dieses Muster "MM/dd/yyyy". Für die Kultur fr-FR lautet es "dd/MM/yyyy". Für die Kultur ja-JP lautet es "yyyy/MM/dd".

Wenn eine Standardformatzeichenfolge in einem Formatierungsvorgang der benutzerdefinierte Formatzeichenfolge einer bestimmten Kultur zugeordnet wird, kann die Anwendung eine bestimmte Kultur definieren, deren benutzerdefinierte Formatzeichenfolgen auf eine der folgenden Weisen verwendet werden:

- Sie können die Standardkultur (die aktuelle Kultur) verwenden. Das folgende Beispiel zeigt ein Datum unter Verwendung des kurzen Datumsformat der aktuellen Kultur an. In diesem Fall ist die aktuelle Kultur en-US.

  [!code-csharp-interactive[System.DateTime.Conceptual.Formatting#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/cs/StandardFormats1.cs#1)]
  [!code-vb[System.DateTime.Conceptual.Formatting#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/vb/StandardFormats1.vb#1)]

- Sie können ein <xref:System.Globalization.CultureInfo>-Objekt, das die Kultur darstellt, deren Formatierung verwendet werden soll, an eine Methode mit einem <xref:System.IFormatProvider>-Parameter übergeben. Das folgenden Beispiel zeigt ein Datum unter Verwendung des kurzen Datumsformat der Kultur pt-BR an.

  [!code-csharp[System.DateTime.Conceptual.Formatting#2](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/cs/StandardFormats1.cs#2)]
  [!code-vb[System.DateTime.Conceptual.Formatting#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/vb/StandardFormats1.vb#2)]

- Sie können ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt, das Formatierungsinformationen liefert, an eine Methode mit einem <xref:System.IFormatProvider>-Parameter übergeben. Das folgenden Beispiel zeigt ein Datum unter Verwendung des kurzen Datumsformat aus einem <xref:System.Globalization.DateTimeFormatInfo>-Objekt für die Kultur hr-HR an.

  [!code-csharp[System.DateTime.Conceptual.Formatting#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/cs/StandardFormats1.cs#3)]
  [!code-vb[System.DateTime.Conceptual.Formatting#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.DateTime.Conceptual.Formatting/vb/StandardFormats1.vb#3)]

> [!NOTE]
> Informationen zum Anpassen der Muster oder Zeichenfolgen, die beim Formatieren der Datums- und Uhrzeitwerte verwendet werden, finden Sie im Thema zur <xref:System.Globalization.NumberFormatInfo>-Klasse.

In einigen Fällen dient die Standardformatzeichenfolge als praktische Abkürzung für eine längere benutzerdefinierte Formatzeichenfolge, die unveränderlich ist. Vier Standardformatzeichenfolgen fallen in diese Kategorie: „O“ (oder „o“), „R“ (oder „r“), „s“ und „u“. Diese Zeichenfolgen entsprechen benutzerdefinierten Formatzeichenfolgen, die durch die invariante Kultur definiert werden. Sie erzeugen Zeichenfolgenentsprechungen von Datums- und Uhrzeitwerten, die über Kulturen hinweg identisch sein sollen. In der folgenden Tabelle werden Informationen über dieses vier Standardformatzeichenfolgen für Datum und Uhrzeit bereitgestellt.

|Standardformatzeichenfolge|Definiert durch die DateTimeFormatInfo.InvariantInfo-Eigenschaft|Benutzerdefinierte Formatzeichenfolge|
|----------------------------|----------------------------------------------------------|--------------------------|
|"O" oder "o"|Keine|yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzz|
|"R" oder "r"|<xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern%2A>|ddd, dd MMM yyyy HH':'mm':'ss 'GMT'|
|"s"|<xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern%2A>|yyyy'-'MM'-'dd'T'HH':'mm':'ss|
|"u"|<xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A>|yyyy'-'MM'-'dd HH':'mm':'ss'Z'|

Standardformatzeichenfolgen können in Analysevorgängen auch mit der <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>-Methode oder mit der <xref:System.DateTimeOffset.ParseExact%2A?displayProperty=nameWithType>-Methode verwendet werden. Dabei muss eine Eingabezeichenfolge genau einem bestimmten Muster entsprechen, damit der Analysevorgang erfolgreich durchgeführt wird. Viele Standardformatzeichenfolgen entsprechen mehreren benutzerdefinierten Formatzeichenfolgen. Ein Datums- und Uhrzeitwert kann also in einer Vielzahl von Formaten dargestellt werden, und dennoch wird der Analysevorgang erfolgreich durchgeführt. Sie können die benutzerdefinierten Formatzeichenfolgen festlegen, die einer Standardformatzeichenfolge entsprechen, indem Sie die <xref:System.Globalization.DateTimeFormatInfo.GetAllDateTimePatterns%28System.Char%29?displayProperty=nameWithType>-Methode aufrufen. Im folgenden Beispiel werden die benutzerdefinierten Formatzeichenfolgen angezeigt, die der Standardformatzeichenfolge "d" (kurzes Datumsmuster) zugeordnet sind.

[!code-csharp[Formatting.DateAndTime.Standard#17](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/stdandparsing1.cs#17)]
[!code-vb[Formatting.DateAndTime.Standard#17](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/stdandparsing1.vb#17)]

In den folgenden Abschnitten werden die Standardformatbezeichner für den <xref:System.DateTime>-Wert und den <xref:System.DateTimeOffset>-Wert beschrieben.

<a name="ShortDate"></a>

## <a name="the-short-date-d-format-specifier"></a>Der Formatbezeichner "d" für das kurze Datum

Der Standardformatbezeichner "d" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>-Eigenschaft einer bestimmten Kultur definiert wird. Die benutzerdefinierte Formatzeichenfolge, die durch die <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>-Eigenschaft der invarianten Kultur zurückgegeben wird, lautet beispielsweise "MM/dd/yyyy".

In der folgenden Tabellen sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>|Definiert das Gesamtformat der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Jahr, Monat und Tag eines Datums trennt.|

Im folgenden Beispiel wird der d-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#1)]
[!code-vb[Formatting.DateAndTime.Standard#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#1)]

[Zurück zur Tabelle](#table)

<a name="LongDate"></a>

## <a name="the-long-date-d-format-specifier"></a>Der Formatbezeichner "D" für langes Datum

Der Standardformatbezeichner "D" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der aktuellen <xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A?displayProperty=nameWithType>-Eigenschaft definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "dddd, dd MMMM yyyy".

In der folgenden Tabelle sind die Eigenschaften des <xref:System.Globalization.DateTimeFormatInfo>-Objekts aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A>|Definiert das Gesamtformat der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Definiert die lokalisierten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.|

Im folgenden Beispiel wird der D-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#2](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#2)]
[!code-vb[Formatting.DateAndTime.Standard#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#2)]

[Zurück zur Tabelle](#table)

<a name="FullDateShortTime"></a>

## <a name="the-full-date-short-time-f-format-specifier"></a>Der Formatbezeichner "f" für vollständiges Datum und kurze Zeit

Der Standardformatbezeichner "f" stellt eine Kombination aus dem Muster für langes Datum ("D") und dem Muster für kurze Zeit ("t") getrennt durch ein Leerzeichen dar.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen eines bestimmten <xref:System.Globalization.DateTimeFormatInfo>-Objekts beeinflusst. In der folgenden Tabelle sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der <xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A?displayProperty=nameWithType>-Eigenschaft und <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType>-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.LongDatePattern%2A>|Definiert das Format der Datumskomponente der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A>|Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Definiert die lokalisierten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Stunde, Minute und Sekunde einer Uhrzeit trennt.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.|

Im folgenden Beispiel wird der f-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#3](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#3)]
[!code-vb[Formatting.DateAndTime.Standard#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#3)]

[Zurück zur Tabelle](#table)

<a name="FullDateLongTime"></a>

## <a name="the-full-date-long-time-f-format-specifier"></a>Der Formatbezeichner "F" für vollständiges Datum und lange Zeit

Der Standardformatbezeichner "F" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der aktuellen <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType>-Eigenschaft definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "dddd, dd MMMM yyyy HH:mm:ss".

In der folgenden Tabelle sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A>-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A>|Definiert das Gesamtformat der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Definiert die lokalisierten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Stunde, Minute und Sekunde einer Uhrzeit trennt.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.|

Im folgenden Beispiel wird der F-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#4](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#4)]
[!code-vb[Formatting.DateAndTime.Standard#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#4)]

[Zurück zur Tabelle](#table)

<a name="GeneralDateShortTime"></a>

## <a name="the-general-date-short-time-g-format-specifier"></a>Der allgemeine Formatbezeichner "g" für Datum und kurze Zeit

Der Standardformatbezeichner "g" stellt eine Kombination aus dem Muster für kurzes Datum ("d") und dem Muster für kurze Zeit ("t") getrennt durch ein Leerzeichen dar.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen eines bestimmten <xref:System.Globalization.DateTimeFormatInfo>-Objekts beeinflusst. In der folgenden Tabelle sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>-Eigenschaft und der <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType>-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>|Definiert das Format der Datumskomponente der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A>|Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Jahr, Monat und Tag eines Datums trennt.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Stunde, Minute und Sekunde einer Uhrzeit trennt.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.|

Im folgenden Beispiel wird der g-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#5](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#5)]
[!code-vb[Formatting.DateAndTime.Standard#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#5)]

[Zurück zur Tabelle](#table)

<a name="GeneralDateLongTime"></a>

## <a name="the-general-date-long-time-g-format-specifier"></a>Der allgemeine Formatbezeichner "G" für Datum und lange Zeit

Der Standardformatbezeichner "G" stellt eine Kombination aus dem Muster für kurzes Datum ("d") und dem Muster für lange Zeit ("T") getrennt durch ein Leerzeichen dar.

Die Ergebniszeichenfolge wird von den Formatierungsinformationen eines bestimmten <xref:System.Globalization.DateTimeFormatInfo>-Objekts beeinflusst. In der folgenden Tabelle sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der <xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A?displayProperty=nameWithType>-Eigenschaft und der <xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A?displayProperty=nameWithType>-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortDatePattern%2A>|Definiert das Format der Datumskomponente der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A>|Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.DateSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Jahr, Monat und Tag eines Datums trennt.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Stunde, Minute und Sekunde einer Uhrzeit trennt.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.|

Im folgenden Beispiel wird der G-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#6](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#6)]
[!code-vb[Formatting.DateAndTime.Standard#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#6)]

[Zurück zur Tabelle](#table)

<a name="MonthDay"></a>

## <a name="the-month-m-m-format-specifier"></a>Der Formatbezeichner "M", "m" für den Monat

Der Standardformatbezeichner "M" oder "m" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der aktuellen <xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern%2A?displayProperty=nameWithType>-Eigenschaft definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "MMMM dd".

In der folgenden Tabellen sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.MonthDayPattern%2A>|Definiert das Gesamtformat der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.|

Im folgenden Beispiel wird der m-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#7](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#7)]
[!code-vb[Formatting.DateAndTime.Standard#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#7)]

[Zurück zur Tabelle](#table)

<a name="Roundtrip"></a>

## <a name="the-round-trip-o-o-format-specifier"></a>Der Formatbezeichner "O", "o" für Roundtrips

Der Standardformatbezeichner "O" oder "o" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit unter Verwendung eines Musters dar, bei dem die Zeitzoneninformationen beibehalten werden, und gibt eine Ergebniszeichenfolge aus, die die Anforderungen von ISO 8601 erfüllt. Für <xref:System.DateTime>-Werte wurde diese Formatzeichenfolge entwickelt, um Datums- und Uhrzeitwerte zusammen mit der <xref:System.DateTime.Kind%2A?displayProperty=nameWithType>-Eigenschaft in Text beizubehalten. Die formatierte Zeichenfolge kann mit der <xref:System.DateTime.Parse%28System.String%2CSystem.IFormatProvider%2CSystem.Globalization.DateTimeStyles%29?displayProperty=nameWithType>-Methode oder mit <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>-Methode rückkonvertiert werden, wenn der `styles`-Parameter auf <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> festgelegt wird.

Der Standardformatbezeichner "O" oder "o" entspricht der benutzerdefinierten Formatzeichenfolge "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffK" für <xref:System.DateTime>-Werte und der benutzerdefinierten Formatzeichenfolge "yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'fffffffzzz" für <xref:System.DateTimeOffset>-Werte. In dieser Zeichenfolge signalisieren die einfachen Anführungszeichen, die einzelne Zeichen wie Bindestriche, Doppelpunkte oder den Buchstaben "T" begrenzen, dass das einzelne Zeichen ein Literal ist, das nicht geändert werden kann. Die Anführungszeichen werden nicht in der Ausgabezeichenfolge angezeigt.

Der Standardformatbezeichner „O“ oder „o“ (und die benutzerdefinierte Formatzeichenfolge „yyyy'-'MM'-'dd'T'HH':'mm':'ss'.fffffffK“) nutzt die drei Methoden, mit denen ISO 8601 Zeitzoneninformationen darstellt, um die <xref:System.DateTime.Kind%2A>-Eigenschaft der <xref:System.DateTime>-Werte beizubehalten:

- Die Zeitzonenkomponente der <xref:System.DateTimeKind.Local?displayProperty=nameWithType>-Datums- und Uhrzeitwerte ist ein Offset von UTC (z. B. +01:00, -07:00). Alle <xref:System.DateTimeOffset>-Werte sind auch in diesem Format dargestellt.

- Die Zeitzonenkomponente der <xref:System.DateTimeKind.Utc?displayProperty=nameWithType>-Datums- und Uhrzeitwerte verwendet "Z" (null Offset), um UTC darzustellen.

- <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType>-Datums- und Uhrzeitwerte enthalten keine Zeitzoneninformationen.

Da der Standardformatbezeichner „O“ oder „o“ einem internationalen Standard entspricht, nutzt der Formatierungs- oder Analysevorgang, der den Bezeichner verwendet, stets die invariante Kultur und den gregorianischen Kalender.

Zeichenfolgen, die an die `Parse`-, `TryParse`-, `ParseExact` und `TryParseExact`-Methoden von <xref:System.DateTime> und <xref:System.DateTimeOffset> weitergegeben werden, können mit dem Formatbezeichner "O" oder "o" analysiert werden, wenn sie in einem dieser Formate vorliegen. Bei <xref:System.DateTime>-Objekten sollte die Überladung, die Sie aufrufen, auch einen `styles`-Parameter mit einem Wert von <xref:System.Globalization.DateTimeStyles.RoundtripKind?displayProperty=nameWithType> enthalten. Beachten Sie, dass Sie durch Aufrufen einer Analysemethode mit der benutzerdefinierten Formatzeichenfolge, die dem Formatbezeichner "O" oder "o" entspricht, nicht die gleichen Ergebnisse wie "O" oder "o" erhalten. Der Grund dafür ist, dass Analysemethoden, die benutzerdefinierte Formatzeichenfolgen verwenden, die Zeichenfolgendarstellung von Datums- und Zeitwerten nicht analysieren können, wenn diese keine Zeitzonenkomponente enthalten oder "Z" zur Angabe von UTC verwenden.

Sie sehen im folgenden Beispiel, dass der „o“-Formatbezeichner zum Anzeigen einer Reihe von <xref:System.DateTime>-Werten und eines <xref:System.DateTimeOffset>-Werts in einem System in der Zeitzone Pacific verwendet wird.

[!code-csharp[Formatting.DateAndTime.Standard#8](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/o1.cs#8)]
[!code-vb[Formatting.DateAndTime.Standard#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/o1.vb#8)]

Im folgenden Beispiel wird der o-Formatbezeichner verwendet, um eine formatierte Zeichenfolge zu erstellen, und anschließend wird der ursprüngliche Datums- und Uhrzeitwert wiederhergestellt, indem eine `Parse`-Methode für Datum und Uhrzeit aufgerufen wird.

[!code-csharp[Formatting.DateandTime.Standard#16](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Roundtrip1.cs#16)]
[!code-vb[Formatting.DateandTime.Standard#16](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/RoundTrip1.vb#16)]

[Zurück zur Tabelle](#table)

<a name="RFC1123"></a>

## <a name="the-rfc1123-r-r-format-specifier"></a>Der RFC1123-Formatbezeichner "R", "r"

Der Standardformatbezeichner "R" oder "r" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der aktuellen <xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern%2A?displayProperty=nameWithType>-Eigenschaft definiert wird. Bei dem Muster handelt es sich um einen definierten Standard. Die Eigenschaft ist schreibgeschützt. Es ist daher unabhängig von der verwendeten Kultur oder dem bereitgestellten Formatanbieter immer identisch. Die benutzerdefinierte Formatzeichenfolge lautet "ddd, dd MMM yyyy HH':'mm':'ss 'GMT'". Wenn dieser Standardformatbezeichner verwendet wird, wird bei der Formatierungs- oder Analysemethode immer die invariante Kultur verwendet.

Die Ergebniszeichenfolge wird von den folgenden Eigenschaften des <xref:System.Globalization.DateTimeFormatInfo>-Objekts beeinflusst, die von der <xref:System.Globalization.DateTimeFormatInfo.InvariantInfo%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wurden, die die invariante Kultur darstellt.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.RFC1123Pattern%2A>|Definiert das Format der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.AbbreviatedDayNames%2A>|Definiert die abgekürzten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.|
|<xref:System.Globalization.DateTimeFormatInfo.AbbreviatedMonthNames%2A>|Definiert die abgekürzten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.|

Auch wenn eine Zeitangabe gemäß der RFC-Spezifikation 1123 als koordinierte Weltzeit (UTC) ausgedrückt wird, wird der Wert des <xref:System.DateTime>-Objekts, das formatiert wird, durch den Formatierungsvorgang nicht geändert. Daher müssen Sie den <xref:System.DateTime>-Wert in UTC konvertieren. Rufen Sie hierfür die <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType>-Methode auf, bevor Sie den Formatierungsvorgang ausführen. Im Gegensatz dazu wird diese Konvertierung durch <xref:System.DateTimeOffset>-Werte automatisch ausgeführt, und es besteht keine Notwendigkeit, die <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType>-Methode vor Ausführung des Formatierungsvorgangs aufzurufen.

Sie sehen im folgenden Beispiel, dass der „r“-Formatbezeichner zum Anzeigen eines <xref:System.DateTime>-Werts und eines <xref:System.DateTimeOffset>-Werts in einem System in der Zeitzone Pacific verwendet wird.

[!code-csharp-interactive[Formatting.DateAndTime.Standard#9](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#9)]
[!code-vb[Formatting.DateAndTime.Standard#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#9)]

[Zurück zur Tabelle](#table)

<a name="Sortable"></a>

## <a name="the-sortable-s-format-specifier"></a>Der sortierbare Formatbezeichner "s"

Der Standardformatbezeichner "s" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der aktuellen <xref:System.Globalization.DateTimeFormatInfo.SortableDateTimePattern%2A?displayProperty=nameWithType>-Eigenschaft definiert wird. Bei dem Muster handelt es sich um einen definierten Standard (ISO 8601). Die Eigenschaft ist schreibgeschützt. Es ist daher unabhängig von der verwendeten Kultur oder dem bereitgestellten Formatanbieter immer identisch. Die benutzerdefinierte Formatzeichenfolge lautet "yyyy'-'MM'-'dd'T'HH':'mm':'ss".

Der Formatbezeichner "s" dient dazu, Ergebniszeichenfolgen zu generieren, die konsistent in aufsteigender oder absteigender Reihenfolge auf der Grundlage von Datums-und Uhrzeitwerten sortieren. Obwohl der Standardformatbezeichner "s" einen Datums- und Uhrzeitwert in einem konsistenten Format darstellt, ändert der Formatierungsvorgang daher nicht den Wert des Datums- und Uhrzeitobjekts, das formatiert wird, entsprechend seiner Eigenschaft <xref:System.DateTime.Kind%2A?displayProperty=nameWithType> oder seines Werts <xref:System.DateTimeOffset.Offset%2A?displayProperty=nameWithType>. Die Ergebniszeichenfolgen, die durch Formatieren der Datums- und Uhrzeitwerte 2014-11-15T18:32:17+00:00 und 2014-11-15T18:32:17+08:00 generiert werden, sind z. B. identisch.

Wenn dieser Standardformatbezeichner verwendet wird, wird bei der Formatierungs- oder Analysemethode immer die invariante Kultur verwendet.

Sie sehen im folgenden Beispiel, dass der „s“-Formatbezeichner zum Anzeigen eines <xref:System.DateTime>-Werts und eines <xref:System.DateTimeOffset>-Werts in einem System in der Zeitzone Pacific verwendet wird.

[!code-csharp-interactive[Formatting.DateAndTime.Standard#10](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#10)]
[!code-vb[Formatting.DateAndTime.Standard#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#10)]

[Zurück zur Tabelle](#table)

<a name="ShortTime"></a>

## <a name="the-short-time-t-format-specifier"></a>Der Formatbezeichner "t" für kurze Zeit

Der Standardformatbezeichner "t" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der aktuellen <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType>-Eigenschaft definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "HH:mm".

Die Ergebniszeichenfolge wird von den Formatierungsinformationen eines bestimmten <xref:System.Globalization.DateTimeFormatInfo>-Objekts beeinflusst. In der folgenden Tabelle sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der <xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A?displayProperty=nameWithType>-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.ShortTimePattern%2A>|Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Stunde, Minute und Sekunde einer Uhrzeit trennt.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.|

Im folgenden Beispiel wird der t-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#11](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#11)]
[!code-vb[Formatting.DateAndTime.Standard#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#11)]

[Zurück zur Tabelle](#table)

<a name="LongTime"></a>

## <a name="the-long-time-t-format-specifier"></a>Der Formatbezeichner "T" für lange Zeit

Der Standardformatbezeichner "T" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der <xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A?displayProperty=nameWithType>-Eigenschaft einer bestimmten Kultur definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "HH:mm:ss".

In der folgenden Tabelle sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der <xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A?displayProperty=nameWithType>-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.LongTimePattern%2A>|Definiert das Format der Zeitkomponente der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Stunde, Minute und Sekunde einer Uhrzeit trennt.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.|

Im folgenden Beispiel wird der T-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#12](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#12)]
[!code-vb[Formatting.DateAndTime.Standard#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#12)]

[Zurück zur Tabelle](#table)

<a name="UniversalSortable"></a>

## <a name="the-universal-sortable-u-format-specifier"></a>Der universelle sortierbare Formatbezeichner "u"

Der Standardformatbezeichner "u" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der aktuellen <xref:System.Globalization.DateTimeFormatInfo.UniversalSortableDateTimePattern%2A?displayProperty=nameWithType>-Eigenschaft definiert wird. Bei dem Muster handelt es sich um einen definierten Standard. Die Eigenschaft ist schreibgeschützt. Es ist daher unabhängig von der verwendeten Kultur oder dem bereitgestellten Formatanbieter immer identisch. Die benutzerdefinierte Formatzeichenfolge lautet "yyyy'-'MM'-'dd HH':'mm':'ss'Z'". Wenn dieser Standardformatbezeichner verwendet wird, wird bei der Formatierungs- oder Analysemethode immer die invariante Kultur verwendet.

Obwohl die Ergebniszeichenfolge eine Zeitangabe als koordinierte Weltzeit (UTC) ausdrücken soll, wird der ursprüngliche <xref:System.DateTime>-Wert während des Formatierungsvorgangs nicht konvertiert. Daher müssen Sie einen <xref:System.DateTime>-Wert in UTC konvertieren, indem Sie die <xref:System.DateTime.ToUniversalTime%2A?displayProperty=nameWithType>-Methode vor dem Formatieren aufrufen.  Im Gegensatz dazu wird diese Konvertierung durch <xref:System.DateTimeOffset>-Werte automatisch ausgeführt, und es besteht keine Notwendigkeit, die <xref:System.DateTimeOffset.ToUniversalTime%2A?displayProperty=nameWithType>-Methode vor Ausführung des Formatierungsvorgangs aufzurufen.

Im folgenden Beispiel wird der u-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp-interactive[Formatting.DateAndTime.Standard#13](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#13)]
[!code-vb[Formatting.DateAndTime.Standard#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#13)]

[Zurück zur Tabelle](#table)

<a name="UniversalFull"></a>

## <a name="the-universal-full-u-format-specifier"></a>Der universelle vollständige Formatbezeichner "U"

Der Standardformatbezeichner "U" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A?displayProperty=nameWithType>-Eigenschaft einer angegebenen Kultur definiert wird. Das Muster ist gleich dem F-Muster. Der <xref:System.DateTime>-Wert wird jedoch vor der Formatierung automatisch in UTC konvertiert.

In der folgenden Tabelle sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern können. Der von der <xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A>-Eigenschaft einiger Kulturen zurückgegebene benutzerdefinierte Formatbezeichner nutzt möglicherweise nicht alle Eigenschaften.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.FullDateTimePattern%2A>|Definiert das Gesamtformat der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.DayNames%2A>|Definiert die lokalisierten Tagesnamen, die in der Ergebniszeichenfolge vorkommen können.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.|
|<xref:System.Globalization.DateTimeFormatInfo.TimeSeparator%2A>|Definiert die Zeichenfolge, die die Komponenten Stunde, Minute und Sekunde einer Uhrzeit trennt.|
|<xref:System.Globalization.DateTimeFormatInfo.AMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mitternacht und Mittag im 12-Stunden-Format angibt.|
|<xref:System.Globalization.DateTimeFormatInfo.PMDesignator%2A>|Definiert die Zeichenfolge, die Zeiten zwischen Mittag und Mitternacht im 12-Stunden-Format angibt.|

Der U-Formatbezeichner wird vom <xref:System.DateTimeOffset>-Typ nicht unterstützt und löst eine <xref:System.FormatException> aus, wenn er zum Formatieren eines <xref:System.DateTimeOffset>-Werts verwendet wird.

Im folgenden Beispiel wird der U-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#14](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#14)]
[!code-vb[Formatting.DateAndTime.Standard#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#14)]

[Zurück zur Tabelle](#table)

<a name="YearMonth"></a>

## <a name="the-year-month-y-y-format-specifier"></a>Der Formatbezeichner "Y", "y" für Jahr-Monat

Der Standardformatbezeichner "Y" oder "y" stellt eine benutzerdefinierte Formatzeichenfolge für Datum und Uhrzeit dar, die von der <xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern%2A?displayProperty=nameWithType>-Eigenschaft einer angegebenen Kultur definiert wird. Die benutzerdefinierte Formatzeichenfolge für die invariante Kultur lautet beispielsweise "yyyy MMMM".

In der folgenden Tabellen sind die <xref:System.Globalization.DateTimeFormatInfo>-Objekteigenschaften aufgeführt, die die Formatierung der zurückgegebenen Zeichenfolge steuern.

|Eigenschaft|Beschreibung|
|--------------|-----------------|
|<xref:System.Globalization.DateTimeFormatInfo.YearMonthPattern%2A>|Definiert das Gesamtformat der Ergebniszeichenfolge.|
|<xref:System.Globalization.DateTimeFormatInfo.MonthNames%2A>|Definiert die lokalisierten Monatsnamen, die in der Ergebniszeichenfolge vorkommen können.|

Im folgenden Beispiel wird der y-Formatbezeichner verwendet, um einen Datums- und Zeitwert anzuzeigen.

[!code-csharp[Formatting.DateAndTime.Standard#15](../../../samples/snippets/csharp/VS_Snippets_CLR/Formatting.DateAndTime.Standard/cs/Standard1.cs#15)]
[!code-vb[Formatting.DateAndTime.Standard#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Formatting.DateAndTime.Standard/vb/Standard1.vb#15)]

[Zurück zur Tabelle](#table)

<a name="Notes"></a>

## <a name="notes"></a>Hinweise

### <a name="control-panel-settings"></a>Einstellungen der Systemsteuerung

Die Einstellungen der **Regions- und Sprachoptionen** in der Systemsteuerung beeinflussen die durch einen Formatierungsvorgang erstellte Ergebniszeichenfolge. Mithilfe dieser Einstellungen wird das <xref:System.Globalization.DateTimeFormatInfo>-Objekt initialisiert, das der aktuellen Threadkultur zugeordnet ist. Sie stellt Werte zur Steuerung der Formatierung bereit. Auf Computern mit anderen Einstellungen werden andere Ergebniszeichenfolgen generiert.

Wenn der <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29?displayProperty=nameWithType> -Constructor verwendet wird, um ein neues <xref:System.Globalization.CultureInfo> -Objekt zu instanziieren, das dieselbe Kultur repräsentiert wie die aktuelle Systemkultur, werden darüber hinaus alle Anpassungen, die über die Einstellung **Regions- und Sprachoptionen** in der Systemsteuerung eingerichtet werden, auf das neue <xref:System.Globalization.CultureInfo> -Objekt angewendet. Sie können den <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29?displayProperty=nameWithType> -Konstruktor verwenden, um ein <xref:System.Globalization.CultureInfo> -Objekt zu erstellen, das die Anpassungen eines Systems nicht wiedergibt.

### <a name="datetimeformatinfo-properties"></a>DateTimeFormatInfo-Eigenschaften

Die Formatierung wird durch die Eigenschaften des aktuellen <xref:System.Globalization.DateTimeFormatInfo>-Objekts beeinflusst, das implizit durch die aktuelle Threadkultur oder explizit durch den <xref:System.IFormatProvider>-Parameter der Methode bereitgestellt wird, die die Formatierung aufruft. Für den <xref:System.IFormatProvider>-Parameter sollte Ihre Anwendung ein <xref:System.Globalization.CultureInfo>-Objekt angeben, das eine Kultur darstellt, oder ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt, das die Formatierungskonventionen für Datum und Uhrzeit einer bestimmten Kultur darstellt. Bei vielen der Standardformatbezeichner für Datum und Uhrzeit handelt es sich um Aliase für Formatierungsmuster, die durch Eigenschaften des aktuellen <xref:System.Globalization.DateTimeFormatInfo>-Objekts definiert werden. Die Anwendung kann das von einigen Standardformatbezeichner für Datum und Uhrzeit erstellte Ergebnis ändern, indem sie die entsprechenden Formatmuster für Datum und Uhrzeit der entsprechenden <xref:System.Globalization.DateTimeFormatInfo>-Eigenschaft ändert.

## <a name="see-also"></a>Siehe auch

- <xref:System.DateTime?displayProperty=nameWithType>
- <xref:System.DateTimeOffset?displayProperty=nameWithType>
- [Formatierung von Typen](../../../docs/standard/base-types/formatting-types.md)
- [Custom Date and Time Format Strings](../../../docs/standard/base-types/custom-date-and-time-format-strings.md)
- [Beispiel: .NET Core-Hilfsprogramm zur Formatierung von WinForms (C#)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-cs)
- [Beispiel: .NET Core-Hilfsprogramm zur Formatierung von WinForms (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/winforms-formatting-utility-vb)
