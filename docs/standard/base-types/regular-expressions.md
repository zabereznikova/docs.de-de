---
title: Reguläre Ausdrücke von .NET
description: Verwenden Sie reguläre Ausdrücke, um in .NET nach bestimmten Zeichenmustern zu suchen, Text zu überprüfen, mit Text-Teilzeichenfolgen zu arbeiten und extrahierte Zeichenfolgen einer Sammlung hinzuzufügen.
ms.date: 06/30/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- pattern-matching with regular expressions, about pattern-matching
- substrings
- searching with regular expressions, about regular expressions
- pattern-matching with regular expressions
- searching with regular expressions
- parsing text with regular expressions
- regular expressions [.NET], about regular expressions
- regular expressions [.NET]
- .NET regular expressions, about
- characters [.NET], regular expressions
- parsing text with regular expressions, overview
- .NET regular expressions
- strings [.NET], regular expressions
ms.assetid: 521b3f6d-f869-42e1-93e5-158c54a6895d
ms.openlocfilehash: 6704ab4a99789e2e0bb4c4336f8c73aa8a89671d
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92888983"
---
# <a name="net-regular-expressions"></a>Reguläre Ausdrücke von .NET

Der Einsatz regulärer Ausdrücke stellt eine leistungsstarke, flexible und effiziente Methode zur Verarbeitung von Text dar. Die umfangreiche Mustervergleichsnotation regulärer Ausdrücke ermöglicht es Ihnen, große Textmengen für folgende Zwecke schnell zu analysieren:

- Suchen nach bestimmten Zeichenmustern
- Überprüfen von Text, um sicherzustellen, dass er einem vordefinierten Muster (z. B. einer E-Mail-Adresse) entspricht
- Extrahieren, Bearbeiten, Ersetzen oder Löschen von Teilzeichenfolgen von Text
- Hinzufügen von extrahierten Zeichenfolgen zu einer Sammlung, um einen Bericht zu generieren

Für viele Anwendungen, die mit Zeichenfolgen arbeiten oder große Textblöcke analysieren, sind reguläre Ausdrücke ein unverzichtbares Tool.  
  
## <a name="how-regular-expressions-work"></a>Funktionsweise von regulären Ausdrücken

 Das Kernstück der Textverarbeitung mit regulären Ausdrücken ist die Engine für reguläre Ausdrücke, die durch das <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>-Objekt in .NET dargestellt wird. Für die Textverarbeitung mit regulären Ausdrücken ist mindestens erforderlich, dass die Engine für reguläre Ausdrücke mit den folgenden zwei Informationen bereitgestellt wird:  
  
- Das Muster des regulären Ausdrucks, das im Text identifiziert werden soll.  
  
     In .NET werden Muster für reguläre Ausdrücke durch eine spezielle Syntax oder Sprache definiert, die mit regulären Ausdrücken in Perl 5 kompatibel ist und einige zusätzliche Funktionen wie Mustervergleiche von rechts nach links bietet. Weitere Informationen finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md).  
  
- Der Text, der nach dem Muster des regulären Ausdrucks analysiert werden soll.  
  
Mit den Methoden der <xref:System.Text.RegularExpressions.Regex>-Klasse können Sie die folgenden Vorgänge durchführen:  
  
- Bestimmen, ob das Muster des regulären Ausdrucks im Eingabetext auftritt, indem die <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType>-Methode aufgerufen wird. Ein Beispiel, in dem Text mithilfe der <xref:System.Text.RegularExpressions.Regex.IsMatch%2A>-Methode überprüft wird, finden Sie unter [Vorgehensweise: Überprüfen, ob Zeichenfolgen ein gültiges E-Mail-Format aufweisen](how-to-verify-that-strings-are-in-valid-email-format.md).  
  
- Abrufen eines oder aller Vorkommen des Texts, die dem Muster des regulären Ausdrucks entsprechen, indem die <xref:System.Text.RegularExpressions.Regex.Match%2A?displayProperty=nameWithType>-Methode oder die <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>-Methode aufgerufen wird. Die erste Methode gibt ein <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType>-Objekt zurück, das Informationen über den übereinstimmenden Text bereitstellt. Die zweite Methode gibt ein <xref:System.Text.RegularExpressions.MatchCollection>-Objekt zurück, das ein <xref:System.Text.RegularExpressions.Match?displayProperty=nameWithType>-Objekt für jede im analysierten Text gefundene Übereinstimmung enthält.  
  
- Ersetzen von Text, der dem Muster des regulären Ausdrucks entspricht, indem die <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>-Methode aufgerufen wird. Beispiele, in denen die <xref:System.Text.RegularExpressions.Regex.Replace%2A>-Methode verwendet wird, um Datumsformate zu ändern und ungültige Zeichen aus einer Zeichenfolge zu entfernen, finden Sie unter [Vorgehensweise: Entfernen von ungültigen Zeichen aus einer Zeichenfolge](how-to-strip-invalid-characters-from-a-string.md) und [Beispiel: Ändern von Datumsformaten](regular-expression-example-changing-date-formats.md).  
  
Eine Übersicht über das Objektmodell für reguläre Ausdrücke finden Sie unter [Das Objektmodell für reguläre Ausdrücke](the-regular-expression-object-model.md).  
  
Weitere Informationen über die Sprache für reguläre Ausdrücke finden Sie unter [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md). Sie können auch eine der folgenden Broschüren herunterladen und ausdrucken:  
  
- [Kurzübersicht im Word-Format (.docx)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
- [Kurzübersicht im PDF-Format (.pdf)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)  
  
## <a name="regular-expression-examples"></a>Beispiele für reguläre Ausdrücke

Die <xref:System.String>-Klasse enthält eine Reihe von Such- und Ersetzungsmethoden für Zeichenfolgen, die Sie verwenden können, wenn Sie Literalzeichenfolgen in einer größeren Zeichenfolge suchen möchten. Reguläre Ausdrücke sind besonders hilfreich, wenn Sie eine von mehreren Teilzeichenfolgen in einer größeren Zeichenfolge suchen oder wenn Sie Muster in einer Zeichenfolge identifizieren möchten, wie in den folgenden Beispielen veranschaulicht wird.

[!INCLUDE [regex](../../../includes/regex.md)]

> [!TIP]
> Der Namespace <xref:System.Web.RegularExpressions> enthält eine Reihe von Objekten für reguläre Ausdrücke, die vordefinierte Muster für reguläre Ausdrucke zum Analysieren von Zeichenfolgen aus HTML-, XML- und ASP.NET-Dokumenten implementieren. Die Klasse <xref:System.Web.RegularExpressions.TagRegex> identifiziert beispielsweise Starttags in einer Zeichenfolge und die Klasse <xref:System.Web.RegularExpressions.CommentRegex> ASP.NET-Kommentare in einer Zeichenfolge.

### <a name="example-1-replace-substrings"></a>Beispiel 1: Ersetzen von Teilzeichenfolgen  

 Angenommen, eine Mailingliste enthält neben dem Vor- und Nachnamen bei einigen Personen auch Angaben zur Anrede (Mr., Mrs., Miss oder Ms.). Wenn Sie Adressaufkleber aus der Liste generieren, die Anrede dabei jedoch unberücksichtigt lassen möchten, können Sie diese mithilfe eines regulären Ausdrucks entfernen, wie im folgenden Beispiel veranschaulicht wird.  
  
 [!code-csharp[Conceptual.Regex#2](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example1.cs#2)]
 [!code-vb[Conceptual.Regex#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example1.vb#2)]  
  
 Das Muster für reguläre Ausdrücke `(Mr\.? |Mrs\.? |Miss |Ms\.? )` entspricht jedem Vorkommen von „Mr “, „Mr. “, „Mrs “, „Mrs. “, „Miss “, „Ms “ oder „Ms. “. Wenn Sie die <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType>-Methode aufrufen, wird die entsprechende Zeichenfolge durch <xref:System.String.Empty?displayProperty=nameWithType> ersetzt, d. h., die Zeichenfolge wird aus der ursprünglichen Zeichenfolge entfernt.  
  
### <a name="example-2-identify-duplicated-words"></a>Beispiel 2: Identifizieren von doppelten Wörtern  

 Das versehentliche Erstellen doppelter Wörter ist ein Fehler, der häufig von Entwicklern gemacht wird. Mithilfe eines regulären Ausdrucks können Sie doppelte Wörter identifizieren, wie im folgenden Beispiel veranschaulicht wird.  
  
 [!code-csharp[Conceptual.Regex#3](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example2.cs#3)]
 [!code-vb[Conceptual.Regex#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example2.vb#3)]  
  
 Das Muster des regulären Ausdrucks `\b(\w+?)\s\1\b` kann wie folgt interpretiert werden:  
  
> [!div class="mx-tdCol2BreakAll"]
> |Muster|Interpretation|  
> |-|-|
> |`\b`|An einer Wortgrenze beginnen.|  
> |`(\w+?)`|Entspricht einem oder mehreren Wortzeichen, aber so wenigen Zeichen wie möglich. Zusammen bilden diese eine Gruppe, auf die mit `\1` verwiesen werden kann.|  
> |`\s`|Entsprechung für ein Leerraumzeichen finden.|  
> |`\1`|Entsprechung für die Teilzeichenfolge finden, die gleich der Gruppe `\1` ist.|  
> |`\b`|Übereinstimmung mit einer Wortgrenze.|  
  
 Die <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType>-Methode wird aufgerufen, und die Optionen für den regulären Ausdruck sind auf <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> festgelegt. Beim Abgleichvorgang spielt die Groß- und Kleinschreibung daher keine Rolle, und die Teilzeichenfolge "This this" wird im Beispiel als Duplikat identifiziert.  
  
 Die Eingabezeichenfolge enthält die Teilzeichenfolge „this? This" enthält. Aufgrund des dazwischenliegenden Satzzeichens wird diese jedoch nicht als Duplikat identifiziert.  
  
### <a name="example-3-dynamically-build-a-culture-sensitive-regular-expression"></a>Beispiel 3: Dynamisches Erstellen eines kulturabhängigen regulären Ausdrucks  

 Das folgende Beispiel veranschaulicht die Leistungsfähigkeit regulärer Ausdrücke in Kombination mit der Flexibilität der .NET-Globalisierungsfunktionen. Mit dem <xref:System.Globalization.NumberFormatInfo>-Objekt wird das Format von Währungswerten in der aktuellen Kultur des Systems bestimmt. Anschließend wird anhand dieser Informationen dynamisch ein regulärer Ausdruck erstellt, der Währungswerte aus dem Text extrahiert. Für jede Übereinstimmung wird die Untergruppe extrahiert, die nur die numerische Zeichenfolge enthält. Diese wird in einen <xref:System.Decimal>-Wert konvertiert, und dann wird ein laufender Gesamtbetrag berechnet.  
  
 [!code-csharp[Conceptual.Regex#1](~/samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex/cs/example.cs#1)]
 [!code-vb[Conceptual.Regex#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex/vb/example.vb#1)]  
  
 Im Beispiel wird dynamisch der reguläre Ausdruck `\$\s*[-+]?([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)` auf einem Computer mit der aktuellen Kultur Englisch - USA (en-US) erstellt. Dieses Muster des regulären Ausdrucks kann wie folgt interpretiert werden:  

> [!div class="mx-tdCol2BreakAll"]
> |Muster|Interpretation|  
> |-|-|  
> |`\$`|Suche nach einem einzelnen Vorkommen des Dollarsymbols (`$`) in der Eingabezeichenfolge. Die Musterzeichenfolge des regulären Ausdrucks schließt einen umgekehrten Schrägstrich ein, der angibt, dass das Dollarsymbol nicht als Anchor des regulären Ausdrucks, sondern wörtlich interpretiert werden soll. (Das `$`-Symbol allein würde angeben, dass die Engine für reguläre Ausdrücke versuchen soll, mit der Suche nach Übereinstimmungen am Ende einer Zeichenfolge zu beginnen.) Um sicherzustellen, dass das Währungssymbol der aktuellen Kultur nicht als reguläres Ausdruckssymbol fehlinterpretiert wird, wird im Beispiel die <xref:System.Text.RegularExpressions.Regex.Escape%2A?displayProperty=nameWithType>-Methode aufgerufen, um das Zeichen mit Escapezeichen zu versehen.|  
> |`\s*`|Suche nach 0 (null) oder mehr Vorkommen eines Leerstellenzeichens.|  
> |`[-+]?`|Suche nach 0 (null) oder einem Vorkommen entweder eines positiven oder eines negativen Vorzeichens.|  
> |`([0-9]{0,3}(,[0-9]{3})*(\.[0-9]+)?)`|Die äußeren Klammern um diesen Ausdruck definieren ihn als Erfassungsgruppe oder Teilausdruck. Wenn eine Übereinstimmung gefunden wird, können Informationen über diesen Teil der übereinstimmenden Zeichenfolge aus dem zweiten <xref:System.Text.RegularExpressions.Group>-Objekt in dem <xref:System.Text.RegularExpressions.GroupCollection>-Objekt abgerufen werden, das von der <xref:System.Text.RegularExpressions.Match.Groups%2A?displayProperty=nameWithType>-Eigenschaft zurückgegeben wird. (Das erste Element in der Auflistung stellt die gesamte Übereinstimmung dar.)|  
> |`[0-9]{0,3}`|Suche nach 0 (null) bis drei Vorkommen der Dezimalstellen 0 bis 9.|  
> |`(,[0-9]{3})*`|Suche nach 0 (null) oder mehr Vorkommen eines Gruppentrennzeichens gefolgt von drei Dezimalstellen.|  
> |`\.`|Suche nach einem einzelnen Vorkommen des Dezimaltrennzeichens.|  
> |`[0-9]+`|Suche nach einer oder mehr Dezimalstellen.|  
> |`(\.[0-9]+)?`|Suche nach 0 (null) oder einem Vorkommen des Dezimaltrennzeichens, auf das mindestens eine Dezimalstelle folgt.|  
  
 Wenn jedes dieser Teilmuster in der Eingabezeichenfolge gefunden wird, ist die Übereinstimmung erfolgreich, und dem <xref:System.Text.RegularExpressions.Match>-Objekt wird ein <xref:System.Text.RegularExpressions.MatchCollection>-Objekt hinzugefügt, das Informationen über die Übereinstimmung enthält.  
  
## <a name="related-topics"></a>Verwandte Themen  
  
|Titel|BESCHREIBUNG|  
|-----------|-----------------|  
|[Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md)|Informationen zu Zeichensatz, Operatoren und Konstrukten, mit denen Sie reguläre Ausdrücke definieren können.|  
|[Das Objektmodell für reguläre Ausdrücke](the-regular-expression-object-model.md)|Ausführliche Informationen und Codebeispiele, die die Verwendung von Klassen für reguläre Ausdrücke veranschaulichen.|  
|[Einzelheiten zum Verhalten regulärer Ausdrücke](details-of-regular-expression-behavior.md)|Ausführliche Informationen zu den Funktionen und dem Verhalten von regulären Ausdrücken in .NET.|
|[Verwenden von regulären Ausdrücken in Visual Studio](/visualstudio/ide/using-regular-expressions-in-visual-studio)||
  
## <a name="reference"></a>Verweis  

- <xref:System.Text.RegularExpressions?displayProperty=nameWithType>  
- <xref:System.Text.RegularExpressions.Regex?displayProperty=nameWithType>  
- [Reguläre Ausdrücke – Kurzübersicht (Download im Word-Format)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.docx)  
- [Reguläre Ausdrücke – Kurzübersicht (Download im PDF-Format)](https://download.microsoft.com/download/D/2/4/D240EBF6-A9BA-4E4F-A63F-AEB6DA0B921C/Regular%20expressions%20quick%20reference.pdf)
