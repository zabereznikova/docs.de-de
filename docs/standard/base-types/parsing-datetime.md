---
title: 'Gewusst wie: Konvertieren von Zeichenfolgen in DateTime-Objekte'
description: Lernen Sie Techniken zum Analysieren von Zeichenfolgen kennen, die Datums- und Uhrzeitwerte repräsentieren, um ein DateTime-Objekt aus der Datums- und Uhrzeitzeichenfolge zu erstellen.
ms.date: 02/15/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- parsing strings, date and time strings
- date and time strings
- ParseExact method
- enumerations [.NET Framework], parsing strings
- base types, parsing strings
- DateTime object
- time strings
ms.openlocfilehash: 9555304e570226b2ed3b040735cf099b5a018f93
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156542"
---
# <a name="parsing-date-and-time-strings-in-net"></a>Analysieren von Zeichenfolgen für Datum und Uhrzeit in .NET

Das Analysieren von Zeichenfolgen für die Konvertierung in <xref:System.DateTime>-Objekte erfordert spezifische Informationen dazu, wie die Datums- und Uhrzeitangaben als Text dargestellt werden. Verschiedene Kulturen verwenden unterschiedliche Reihenfolgen für Tag, Monat und Jahr. Einige Uhrzeiten werden im 24-Stunden-Format dargestellt, andere verwenden Zusätze wie „AM“ und „PM“. Einige Anwendungen erfordern nur das Datum. Für andere ist ausschließlich die Uhrzeit erforderlich. Für wieder andere Anwendungen muss sowohl das Datum als auch die Uhrzeit angegeben werden. Die Methoden zum Konvertieren von Zeichenfolgen in <xref:System.DateTime>-Objekte ermöglichen es Ihnen, detaillierte Informationen zu den erwarteten Formaten und den Datums- und Uhrzeitelementen anzugeben, die für Ihre Anwendung benötigt werden. Es gibt drei Unteraufgaben zum ordnungsgemäßen Konvertieren von Text in ein <xref:System.DateTime>-Objekt:

1. Sie müssen das erwartete Format für den Text angeben, mit dem ein Datum und eine Uhrzeit repräsentiert werden.
1. Sie können die Kultur für das Format eines Datums-/Uhrzeitwerts angeben.
1. Sie können angeben, wie fehlende Komponenten in der Textdarstellung in Datum und Uhrzeit festgelegt werden.

Die Methoden <xref:System.DateTime.Parse%2A> und <xref:System.DateTime.TryParse%2A> ermöglichen eine Konvertierung zahlreicher gängiger Darstellungen von Datum und Uhrzeit. Die Methoden <xref:System.DateTime.ParseExact%2A> und <xref:System.DateTime.TryParseExact%2A> konvertieren eine Zeichenfolgendarstellung entsprechend dem Muster, das durch eine Formatzeichenfolge für Datum und Uhrzeit angegeben wird. (Ausführliche Informationen hierzu finden Sie in den Artikeln [Standard-Formatzeichenfolgen für Datum und Uhrzeit](standard-date-and-time-format-strings.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-date-and-time-format-strings.md).)

Das aktuelle <xref:System.Globalization.DateTimeFormatInfo>-Objekt bietet mehr Kontrolle darüber, wie der Text als Datum und Uhrzeit interpretiert werden soll. Die Eigenschaften eines <xref:System.Globalization.DateTimeFormatInfo>-Objekts beschreiben die Trennzeichen für Datum und Uhrzeit, die Namen von Monaten, Tagen und Zeiträumen sowie das Format der Bezeichnung „AM“ und „PM“. Die aktuelle Threadkultur stellt ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt bereit, das die aktuelle Kultur repräsentiert. Wenn Sie eine bestimmte Kultur oder benutzerdefinierte Einstellungen verwenden möchten, geben Sie den Parameter <xref:System.IFormatProvider> einer Analysemethode an. Geben Sie für den <xref:System.IFormatProvider>-Parameter ein <xref:System.Globalization.CultureInfo>-Objekt an, das eine Kultur darstellt, oder ein <xref:System.Globalization.DateTimeFormatInfo>-Objekt.

Im Text zur Darstellung eines Datums oder einer Uhrzeit fehlen möglicherweise Informationen. Beispielsweise würden die meisten Personen annehmen, dass mit „12. März“ das aktuelle Jahr gemeint ist. Ebenso repräsentiert „März 2018“ den Monat März im Jahr 2018. Der Text zur Darstellung einer Uhrzeit enthält häufig nur die Stunden und Minuten sowie eine AM/PM-Bezeichnung.  Analysemethoden verarbeiten diese fehlenden Informationen, indem sie geeignete Standardwerte verwenden:

- Wenn nur die Uhrzeit vorhanden ist, wird für den Datumsteil das aktuelle Datum verwendet.
- Wenn nur das Datum vorhanden ist, wird für den Uhrzeitteil Mitternacht verwendet.
- Wenn in einem Datum kein Jahr angegeben ist, wird das aktuelle Jahr verwendet.
- Wenn kein Tag des Monats angegeben ist, wird der erste Tag des Monats verwendet.

Wenn das Datum in der Zeichenfolge enthalten ist, muss es den Monat und einen Tag oder ein Jahr enthalten. Wenn die Uhrzeit enthalten ist, muss die Stundenangabe und entweder eine Minutenangabe oder die Bezeichnung „AM/PM“ enthalten sein.

Sie können die Konstante <xref:System.Globalization.DateTimeStyles.NoCurrentDateDefault> angeben, um diese Standardeinstellungen außer Kraft zu setzen. Wenn Sie diese Konstante verwenden, werden alle fehlenden Eigenschaften für Jahr, Monat oder Tag auf den Wert `1` festgelegt. Dieses Verhalten wird im [letzten Beispiel](#styles-example) durch die Verwendung von <xref:System.DateTime.Parse%2A> veranschaulicht.

Zusätzlich zu einer Datums- und Zeitkomponente kann die Zeichenfolgendarstellung einer Datums- und Uhrzeitangabe einen Zeitraum enthalten, der angibt, um wie viel die Zeit von der koordinierten Weltzeit (UTC) abweicht. Beispielsweise definiert die Zeichenfolge „2/14/2007 5:32:00 -7:00“ eine Uhrzeit, die sieben Stunden vor UTC liegt. Wenn die Abweichung in der Zeichenfolgendarstellung einer Uhrzeit fehlt, gibt die Analyse ein <xref:System.DateTime>-Objekt zurück, dessen <xref:System.DateTime.Kind%2A>-Eigenschaft auf <xref:System.DateTimeKind.Unspecified?displayProperty=nameWithType> festgelegt ist. Wird eine Abweichung angegeben, gibt die Analyse ein <xref:System.DateTime>-Objekt zurück, dessen <xref:System.DateTime.Kind%2A>-Eigenschaft auf <xref:System.DateTimeKind.Local?displayProperty=nameWithType> festgelegt ist und dessen Wert an die lokale Zeitzone des Computers angepasst wird. Sie können dieses Verhalten ändern, indem Sie einen <xref:System.Globalization.DateTimeStyles>-Wert mit der Analysemethode verwenden.
  
Der Formatanbieter wird auch zum Interpretieren mehrdeutiger numerischer Datumsangaben verwendet. Es ist nicht eindeutig zu erkennen, welche Komponenten des in der Zeichenfolge „02/03/04“ dargestellten Datums für den Monat, den Tag und das Jahr stehen. Die Komponenten werden entsprechend der Reihenfolge ähnlicher Datumsformate im Formatanbieter interpretiert.

## <a name="parse"></a>Parse

Das folgende Codebeispiel veranschaulicht die Verwendung der <xref:System.DateTime.Parse%2A?displayProperty=nameWithType>-Methode zum Konvertieren eines `string`-Werts in ein <xref:System.DateTime>-Objekt. In diesem Beispiel wird die dem aktuellen Thread zugeordnete Kultur verwendet. Wenn die der aktuellen Kultur zugeordnete <xref:System.Globalization.CultureInfo>-Klasse nicht die Eingabezeichenfolge analysieren kann, wird eine <xref:System.FormatException> ausgelöst.

> [!TIP]
> Alle C#-Beispiele in diesem Artikel werden in Ihrem Browser ausgeführt. Klicken Sie auf die Schaltfläche **Ausführen**, um die Ausgabe anzuzeigen. Sie können auch Bearbeitungen vornehmen, um ein wenig zu experimentieren.

> [!NOTE]
> Diese Beispiele sind im GitHub-docs-Repository sowohl für [C#](https://github.com/dotnet/samples/tree/master/snippets/csharp/how-to/conversions) als auch für [Visual Basic](https://github.com/dotnet/samples/tree/master/snippets/visualbasic/how-to/conversions) verfügbar. Alternativ können Sie das Projekt als ZIP-Datei für [C#](https://github.com/dotnet/samples/raw/master/snippets/csharp/how-to/conversions.zip) oder [Visual Basic](https://github.com/dotnet/samples/raw/master/snippets/visualbasic/how-to/conversions.zip) herunterladen.

[!code-csharp-interactive[Parsing.DateAndTime#1](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#1)]
[!code-vb[Parsing.DateAndTime#1](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#1)]

Sie können beim Analysieren einer Zeichenfolge auch explizit die Kultur angeben, deren Formatierungskonventionen verwendet werden sollen. Sie geben eines der <xref:System.Globalization.DateTimeFormatInfo>-Standardobjekte an, die von der Eigenschaft <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType> zurückgegeben werden. Im folgenden Beispiel wird ein Formatanbieter verwendet, um eine deutsche Zeichenfolge zu analysieren und in ein <xref:System.DateTime>-Objekt zu konvertieren. Es wird ein <xref:System.Globalization.CultureInfo>-Objekt erstellt, das die Kultur `de-DE` darstellt. Dieses `CultureInfo`-Objekt sorgt für eine erfolgreiche Analyse der Zeichenfolge. Hierdurch wird jegliche Einstellung in der <xref:System.Threading.Thread.CurrentCulture> von <xref:System.Threading.Thread.CurrentThread> ausgeschlossen.  
  
[!code-csharp[Parsing.DateAndTime#2](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#2)]
[!code-vb[Parsing.DateAndTime#2](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#2)]

Auch wenn Sie Überladungen der <xref:System.DateTime.Parse%2A>-Methode zur Angabe benutzerdefinierter Formatanbieter verwenden können, bietet die Methode keine Unterstützung für das Analysieren von Formaten, die nicht dem Standard entsprechen. Um ein Datum und eine Uhrzeit in einem nicht dem Standard entsprechenden Format zu analysieren, verwenden Sie stattdessen die <xref:System.DateTime.ParseExact%2A>-Methode.  

<a name="styles-example"></a>Im folgenden Codebeispiel wird anhand der <xref:System.Globalization.DateTimeStyles>-Enumeration angegeben, dass die aktuellen Datums- und Uhrzeitinformationen nur für angegebene Felder dem <xref:System.DateTime>-Objekt hinzugefügt werden sollen.  

[!code-csharp[Parsing.DateAndTime#3](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#3)]
[!code-vb[Parsing.DateAndTime#3](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#3)]

## <a name="parseexact"></a>ParseExact

Die Methode <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType> konvertiert eine Zeichenfolge in ein <xref:System.DateTime>-Objekt, wenn es einem der angegebenen Zeichenfolgenmuster entspricht. Wird eine Zeichenfolge an diese Methode übergeben, die nicht dem angegebenen Format entspricht, wird eine <xref:System.FormatException> ausgelöst. Sie können einen der Standardformatbezeichner für Datum und Uhrzeit oder eine Kombination der benutzerdefinierten Formatbezeichner angeben. Mithilfe der benutzerdefinierten Formatbezeichner können Sie eine benutzerdefinierte Erkennungszeichenfolge erstellen. Erläuterungen zu den Bezeichnern finden Sie in den Themen [Standardformatzeichenfolgen für Datum und Uhrzeit](standard-date-and-time-format-strings.md) und [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-date-and-time-format-strings.md).  

Im folgenden Codebeispiel wird die <xref:System.DateTime.ParseExact%2A?displayProperty=nameWithType>-Methode an ein zu analysierendes Zeichenfolgenobjekt übergeben, gefolgt von einem Formatbezeichner und einem <xref:System.Globalization.CultureInfo>-Objekt. Diese <xref:System.DateTime.ParseExact%2A>-Methode kann nur Zeichenfolgen analysieren, die dem langen Datumsmuster in der Kultur `en-US` entsprechen.  

[!code-csharp[Parsing.DateAndTime#4](../../../samples/snippets/csharp/how-to/conversions/StringToDateTime.cs#4)]
[!code-vb[Parsing.DateAndTime#4](../../../samples/snippets/visualbasic/how-to/conversions/Program.vb#4)]

Jede Überladung der Methode <xref:System.DateTime.Parse%2A> und <xref:System.DateTime.ParseExact%2A> umfasst auch einen <xref:System.IFormatProvider>-Parameter, der kulturspezifische Informationen zur Formatierung der Zeichenfolge enthält. In der Regel handelt es sich bei diesem <xref:System.IFormatProvider>-Objekt um ein <xref:System.Globalization.CultureInfo>-Objekt, das eine Standardkultur oder ein von der Eigenschaft <xref:System.Globalization.DateTimeFormatInfo> zurückgegebenes <xref:System.Globalization.CultureInfo.DateTimeFormat%2A?displayProperty=nameWithType>-Objekt darstellt.  <xref:System.DateTime.ParseExact%2A> verwendet außerdem ein zusätzliches Zeichenfolgen- oder Zeichenfolgenarrayargument, mit dem mindestens ein benutzerdefiniertes Datums- und Uhrzeitformat definiert wird.  

## <a name="see-also"></a>Siehe auch

- [Analysieren von Zeichenfolgen in .NET](parsing-strings.md)
- [Formatierung von Typen](formatting-types.md)
- [Typkonvertierung in .NET](type-conversion.md)
- [Standard-Formatzeichenfolgen für Datum und Uhrzeit](standard-date-and-time-format-strings.md)
- [Benutzerdefinierte Formatzeichenfolgen für Datum und Uhrzeit](custom-date-and-time-format-strings.md)
