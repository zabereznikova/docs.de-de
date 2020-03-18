---
title: Ersetzungen in regulären Ausdrücken
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- regular expressions, substitutions
- replacement patterns
- metacharacters, substitutions
- .NET Framework regular expressions, substitutions
- constructs, substitutions
- substitutions
ms.assetid: d1f52431-1c7d-4dc6-8792-6b988256892e
ms.openlocfilehash: 3562bd113ae4c9a3f721d8858a5d3625ef548d3a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/15/2020
ms.locfileid: "78160077"
---
# <a name="substitutions-in-regular-expressions"></a>Ersetzungen in regulären Ausdrücken
Ersetzungen sind Sprachelemente, die nur in Ersetzungsmustern erkannt werden. Sie definieren den gesamten Text oder einen Teil des Texts, der den entsprechenden Text in der Eingabezeichenfolge ersetzen soll, mithilfe eines Musters eines regulären Ausdrucks. Das Ersetzungsmuster kann zusammen mit Literalzeichen aus einer oder mehreren Ersetzungen bestehen. Ersetzungsmuster werden für Überladungen der <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> -Methode bereitgestellt, die über einen `replacement` -Parameter verfügen, und für die <xref:System.Text.RegularExpressions.Match.Result%2A?displayProperty=nameWithType> -Methode. Die Methoden ersetzen das übereinstimmende Muster durch das Muster, das durch den `replacement` -Parameter definiert wird.  
  
 .NET Framework definiert die in der folgenden Tabelle aufgeführten Ersetzungselemente.  
  
|Substitution|Beschreibung|  
|------------------|-----------------|  
|$ *Zahl*|Schließt die letzte mit der Erfassungsgruppe, die durch *Zahl*identifiziert wird, übereinstimmende Teilzeichenfolge in der Ersetzungszeichenfolge ein. Hierbei ist *Zahl* ein Dezimalwert. Weitere Informationen finden Sie unter [Ersetzen einer nummerierten Gruppe](#substituting-a-numbered-group).|  
|${ *Name* }|Schließt die letzte Teilzeichenfolge in der Ersetzungszeichenfolge ein, die von der benannten Gruppe gefunden wird, die mit `(?<`*Name*`> )` angegeben wird. Weitere Informationen finden Sie unter [Ersetzen einer benannten Gruppe](#substituting-a-named-group).|  
|$$|Schließt ein einzelnes "$"-Literal in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen eines "$"-Symbols](#substituting-a--character).|  
|$&|Schließt eine Kopie der gesamten Übereinstimmung in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen der gesamten Übereinstimmung](#substituting-the-entire-match).|  
|$\`|Schließt den gesamten Text der Eingabezeichenfolge vor der Übereinstimmung in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen des Texts vor der Übereinstimmung](#substituting-the-text-before-the-match).|  
|$'|Schließt den gesamten Text der Eingabezeichenfolge nach der Übereinstimmung in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen des Texts nach der Übereinstimmung](#substituting-the-text-after-the-match).|  
|$+|Schließt die letzte erfasste Gruppe in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen der zuletzt erfassten Gruppe](#substituting-the-last-captured-group).|  
|$\_|Schließt die gesamte Eingabezeichenfolge in der Ersetzungszeichenfolge ein. Weitere Informationen finden Sie unter [Ersetzen der ganzen Eingabezeichenfolge](#substituting-the-entire-input-string).|  
  
## <a name="substitution-elements-and-replacement-patterns"></a>Ersetzungselemente und Ersetzungsmuster  
 Ersetzungen sind die einzigen Sonderkonstrukte, die in einem Ersetzungsmuster erkannt werden. Keines der anderen Sprachelemente für reguläre Ausdrücke, einschließlich Escapezeichen und Punkt (`.`), der einem beliebigen Zeichen entspricht, wird unterstützt. Auf ähnliche Weise werden Ersetzungssprachelemente nur in Ersetzungsmustern erkannt und sind in Mustern für reguläre Ausdrücke nie gültig.  
  
 Das einzige Zeichen, das entweder in einem Muster eines regulären Ausdrucks oder in einer Ersetzung vorkommen kann, ist das `$` -Zeichen, obwohl es in jedem Kontext eine andere Bedeutung hat. In einem Muster eines regulären Ausdrucks ist `$` ein Anker, der dem Ende der Zeichenfolge entspricht. In einem Ersetzungsmuster gibt `$` den Anfang einer Ersetzung an.  
  
> [!NOTE]
> Für die Funktionalität, die mit einem Ersetzungsmuster innerhalb eines regulären Ausdrucks vergleichbar ist, verwenden Sie einen Rückverweis. Weitere Informationen zu Rückverweisen finden Sie unter [Rückverweiskonstrukte](../../../docs/standard/base-types/backreference-constructs-in-regular-expressions.md).  

## <a name="substituting-a-numbered-group"></a>Ersetzen einer nummerierten Gruppe  
 Das `$`*Zahl* -Sprachelement schließt die letzte Teilzeichenfolge ein, die mit der *Zahl* -Erfassungsgruppe in der Ersetzungszeichenfolge übereinstimmt, wobei *Zahl* der Index der Erfassungsgruppe ist. Beispielsweise gibt das Ersetzungsmuster `$1` an, dass die übereinstimmende Teilzeichenfolge durch die erste erfasste Gruppe ersetzt werden soll. Weitere Informationen zu nummerierten Erfassungsgruppen finden Sie unter [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
 Alle Ziffern, die auf `$` folgen, werden als zur Gruppe *Zahl* gehörend interpretiert. Wenn dies nicht Ihre Absicht ist, können Sie stattdessen eine benannte Gruppe ersetzen. Sie können z. B. die Ersetzungszeichenfolge `${1}1` anstelle von `$11` verwenden, um die Ersetzungszeichenfolge als Wert der ersten erfassten Gruppe zusammen mit der Nummer "1" zu definieren. Weitere Informationen finden Sie unter [Ersetzen einer benannten Gruppe](#substituting-a-named-group).  
  
 Erfassungsgruppen, denen mit der Syntax `(?<`*Name*`>)` keine Namen explizit zugewiesen sind, werden beginnend mit Eins von links nach rechts durchnummeriert. Auch benannte Gruppen werden von links nach rechts durchnummeriert, wobei der Startwert um eins größer ist als der Index der letzten unbenannten Gruppe. Im regulären Ausdruck `(\w)(?<digit>\d)`ist z. B. der Index der benannten Gruppe `digit` 2.  
  
 Wenn *Zahl* keine gültige Erfassungsgruppe angibt, die in den regulären Ausdrucksmustern definiert sind, wird `$`*Zahl* als Literalzeichensequenz interpretiert, die zum Ersetzen der einzelnen Übereinstimmungen verwendet wird.  
  
 Das folgende Beispiel verwendet die `$`*Zahl* -Ersetzung, um das aktuelle Symbol aus einem Dezimalwert zu extrahieren. Sie entfernt am Anfang oder Ende eines Währungswerts gefundene Währungssymbole und erkennt die zwei häufigsten Dezimaltrennzeichen ("." und ",").  
  
 [!code-csharp[Conceptual.RegEx.Language.Substitutions#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/numberedgroup1.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.Substitutions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/numberedgroup1.vb#1)]  
  
 Das Muster für reguläre Ausdrücke `\p{Sc}*(\s?\d+[.,]?\d*)\p{Sc}*` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\p{Sc}*`|Übereinstimmung mit keinem oder mehreren Währungssymbolzeichen.|  
|`\s?`|Sucht nach einer Übereinstimmung mit keinem oder einem Leerzeichen.|  
|`\d+`|Entsprechung für mindestens eine Dezimalstelle finden.|  
|`[.,]?`|Übereinstimmung mit keinem oder einem Punkt oder Komma.|  
|`\d*`|0 (null) oder mehr Dezimalstellen sollen übereinstimmen.|  
|`(\s?\d+[.,]?\d*)`|Übereinstimmung mit einem Leerzeichen, gefolgt von mindestens einer Dezimalstelle, gefolgt von keinem oder einem Punkt oder Komma, gefolgt von keiner oder mehreren Dezimalstellen. Dies ist die erste Erfassungsgruppe. Da das Ersetzungsmuster `$1`ist, ersetzt der Aufruf der <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> -Methode die gesamte übereinstimmende Teilzeichenfolge durch diese erfasste Gruppe.|  

## <a name="substituting-a-named-group"></a>Ersetzen einer benannten Gruppe  
 Das `${`*Name*`}` -Sprachelement ersetzt die letzte mit der Erfassungsgruppe *Name* übereinstimmende Teilzeichenfolge, wobei *Name* der Name einer Erfassungsgruppe ist, die durch das Sprachelement `(?<`*Name*`>)` definiert wird. Weitere Informationen zu benannten Erfassungsgruppen finden Sie unter [Grouping Constructs](../../../docs/standard/base-types/grouping-constructs-in-regular-expressions.md).  
  
 Wenn *Name* keine im Muster eines regulären Ausdrucks definierte gültige benannte Erfassungsgruppe angibt, aber aus Ziffern besteht, wird `${`*Name*`}` als eine nummerierte Gruppe interpretiert.  
  
 Wenn *Name* weder eine im Muster eines regulären Ausdrucks definierte gültige benannte Erfassungsgruppe noch eine gültige nummerierte Erfassungsgruppe angibt, wird `${`*Name*`}` als Literalzeichensequenz interpretiert, die verwendet wird, um alle Übereinstimmungen zu ersetzen.  
  
 Im folgenden Beispiel wird die `${`*Name*`}` -Ersetzung verwendet, um das Währungssymbol aus einem Dezimalwert zu entfernen. Sie entfernt am Anfang oder Ende eines Währungswerts gefundene Währungssymbole und erkennt die zwei häufigsten Dezimaltrennzeichen ("." und ",").  
  
 [!code-csharp[Conceptual.RegEx.Language.Substitutions#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/namedgroup1.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.Substitutions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/namedgroup1.vb#2)]  
  
 Das Muster für reguläre Ausdrücke `\p{Sc}*(?<amount>\s?\d[.,]?\d*)\p{Sc}*` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\p{Sc}*`|Übereinstimmung mit keinem oder mehreren Währungssymbolzeichen.|  
|`\s?`|Sucht nach einer Übereinstimmung mit keinem oder einem Leerzeichen.|  
|`\d+`|Entsprechung für mindestens eine Dezimalstelle finden.|  
|`[.,]?`|Übereinstimmung mit keinem oder einem Punkt oder Komma.|  
|`\d*`|0 (null) oder mehr Dezimalstellen sollen übereinstimmen.|  
|`(?<amount>\s?\d[.,]?\d*)`|Übereinstimmung mit einem Leerzeichen, gefolgt von mindestens einer Dezimalstelle, gefolgt von keinem oder einem Punkt oder Komma, gefolgt von keiner oder mehreren Dezimalstellen. Dies ist die Erfassungsgruppe mit dem Namen `amount`. Da das Ersetzungsmuster `${amount}`ist, ersetzt der Aufruf der <xref:System.Text.RegularExpressions.Regex.Replace%2A?displayProperty=nameWithType> -Methode die gesamte übereinstimmende Teilzeichenfolge durch diese erfasste Gruppe.|  

## <a name="substituting-a--character"></a>Ersetzen eines "$"-Zeichens  
 Die `$$` -Ersetzung fügt ein literales "$"-Zeichen in der ersetzten Zeichenfolge ein.  
  
 Im folgenden Beispiel werden das Währungssymbol der aktuellen Kultur und seine Platzierung in einer Währungszeichenfolge mithilfe des <xref:System.Globalization.NumberFormatInfo> -Objekts bestimmt. Anschließend werden sowohl ein Muster eines regulären Ausdrucks als auch ein Ersetzungsmuster dynamisch erstellt. Wenn das Beispiel auf einem Computer ausgeführt wird, dessen aktuelle Kultur en-US ist, werden das Muster eines regulären Ausdrucks `\b(\d+)(\.(\d+))?` und das Ersetzungsmuster `$$ $1$2`generiert. Das Ersetzungsmuster ersetzt den übereinstimmenden Text durch ein Währungssymbol und ein Leerzeichen, gefolgt von der ersten und zweiten erfassten Gruppe.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/dollarsign1.cs#8)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/dollarsign1.vb#8)]  
  
 Das Muster für reguläre Ausdrücke `\b(\d+)(\.(\d+))?` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Beginnt den Abgleich am Anfang einer Wortgrenze.|  
|`(\d+)`|Entsprechung für mindestens eine Dezimalstelle finden. Dies ist die erste Erfassungsgruppe.|  
|`\.`|Übereinstimmung mit einem Punkt (dem Dezimaltrennzeichen).|  
|`(\d+)`|Entsprechung für mindestens eine Dezimalstelle finden. Dies ist die dritte Erfassungsgruppe.|  
|`(\.(\d+))?`|Übereinstimmung mit keinem oder einem Vorkommen eines Punkts gefolgt von mindestens einer Dezimalzahl. Dies ist die zweite Erfassungsgruppe.|  

## <a name="substituting-the-entire-match"></a>Ersetzen der gesamten Übereinstimmung  
 Die Ersetzung `$&` schließt die gesamte Übereinstimmung in die Ersetzungszeichenfolge ein. Sie wird häufig dazu verwendet, dem Anfang oder Ende der übereinstimmenden Zeichenfolge eine Teilzeichenfolge hinzuzufügen. Das Ersetzungsmuster `($&)` fügt z. B. dem Anfang und Ende jeder Übereinstimmung Klammern hinzu. Wenn keine Übereinstimmung vorhanden ist, wirkt sich die Ersetzung `$&` nicht aus.  
  
 Im folgenden Beispiel werden mithilfe der Ersetzung `$&` Anführungszeichen am Anfang und Ende von Buchtiteln hinzugefügt, die in einem Zeichenfolgenarray gespeichert wurden.  
  
 [!code-csharp[Conceptual.RegEx.Language.Substitutions#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/entirematch1.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.Substitutions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/entirematch1.vb#3)]  
  
 Das Muster für reguläre Ausdrücke `^(\w+\s?)+$` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Beginnt den Abgleich am Anfang der Eingabezeichenfolge.|  
|`(\w+\s?)+`|Übereinstimmung mit dem Muster mindestens eines Wortzeichens, ein- oder mehrmals gefolgt von einer Null oder einem Leerzeichen.|  
|`$`|Entsprechung für das Ende der Eingabezeichenfolge finden.|  
  
 Das Ersetzungsmuster `"$&"` fügt dem Anfang und Ende jeder Übereinstimmung ein literales Anführungszeichen hinzu.  

## <a name="substituting-the-text-before-the-match"></a>Ersetzen des Texts vor der Übereinstimmung  
 Die Ersetzung ``$` `` ersetzt die übereinstimmende Zeichenfolge vor der Übereinstimmung durch die gesamte Eingabezeichenfolge. Das heißt, die Eingabezeichenfolge wird bis zur Übereinstimmung dupliziert, während der übereinstimmende Text entfernt wird. Jeder Text, der dem übereinstimmenden Text folgt, bleibt in der Ergebniszeichenfolge unverändert. Wenn mehrere Übereinstimmungen in einer Eingabezeichenfolge vorhanden sind, wird der Ersetzungstext von der ursprünglichen Eingabezeichenfolge abgeleitet und nicht von der Zeichenfolge, in der Text durch frühere Übereinstimmungen ersetzt wurde. \(Dies wird im Beispiel veranschaulicht.\) Wenn keine Übereinstimmung vorhanden ist, wirkt sich die Ersetzung ``$` `` nicht aus.  
  
 Im folgenden Beispiel wird eine Sequenz von einer oder mehreren Dezimalstellen in der Eingabezeichenfolge mithilfe des Muster eines regulären Ausdrucks `\d+` abgeglichen. Die Ersetzungszeichenfolge ``$` `` ersetzt diese Ziffern durch den Text, der der Übereinstimmung vorausgeht.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/before1.cs#4)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/before1.vb#4)]  
  
 In diesem Beispiel enthält die Eingabezeichenfolge `"aa1bb2cc3dd4ee5"` fünf Übereinstimmungen. Aus der folgenden Tabelle wird ersichtlich, wie die Ersetzung ``$` `` bewirkt, dass die Engine für reguläre Ausdrücke jede Übereinstimmung in der Eingabezeichenfolge ersetzt. Eingefügter Text wird in der Ergebnisspalte in Fettdruck angezeigt.  
  
|Match|Position|Zeichenfolge vor Übereinstimmung|Ergebniszeichenfolge|  
|-----------|--------------|-------------------------|-------------------|  
|1|2|aa|aa**aa**bb2cc3dd4ee5|  
|2|5|aa1bb|aaaabb**aa1bb**cc3dd4ee5|  
|3|8|aa1bb2cc|aaaabbaa1bbcc**aa1bb2cc**dd4ee5|  
|4|11|aa1bb2cc3dd|aaaabbaa1bbccaa1bb2ccdd**aa1bb2cc3dd**ee5|  
|5|14|aa1bb2cc3dd4ee|aaaabbaa1bbccaa1bb2ccddaa1bb2cc3ddee**aa1bb2cc3dd4ee**|

## <a name="substituting-the-text-after-the-match"></a>Ersetzen des Texts nach der Übereinstimmung  
 Die Ersetzung `$'` ersetzt die übereinstimmende Zeichenfolge nach der Übereinstimmung durch die gesamte Eingabezeichenfolge. Das heißt, die Eingabezeichenfolge wird nach der Übereinstimmung dupliziert, während der übereinstimmende Text entfernt wird. Jeder Text, der dem übereinstimmenden Text vorausgeht, bleibt in der Ergebniszeichenfolge unverändert. Wenn keine Übereinstimmung vorhanden ist, wirkt sich die Ersetzung  `$'` nicht aus.  
  
 Im folgenden Beispiel wird eine Sequenz von einer oder mehreren Dezimalstellen in der Eingabezeichenfolge mithilfe des Muster eines regulären Ausdrucks `\d+` abgeglichen. Der Ersetzungszeichenfolge `$'` ersetzt diese Ziffern durch den Text, der der Übereinstimmung folgt.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/after1.cs#5)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/after1.vb#5)]  
  
 In diesem Beispiel enthält die Eingabezeichenfolge `"aa1bb2cc3dd4ee5"` fünf Übereinstimmungen. Aus der folgenden Tabelle wird ersichtlich, wie die Ersetzung `$'` bewirkt, dass die Engine für reguläre Ausdrücke jede Übereinstimmung in der Eingabezeichenfolge ersetzt. Eingefügter Text wird in der Ergebnisspalte in Fettdruck angezeigt.  
  
|Match|Position|Zeichenfolge nach Übereinstimmung|Ergebniszeichenfolge|  
|-----------|--------------|------------------------|-------------------|  
|1|2|bb2cc3dd4ee5|aa**bb2cc3dd4ee5**bb2cc3dd4ee5|  
|2|5|cc3dd4ee5|aabb2cc3dd4ee5bb**cc3dd4ee5**cc3dd4ee5|  
|3|8|dd4ee5|aabb2cc3dd4ee5bbcc3dd4ee5cc**dd4ee5**dd4ee5|  
|4|11|ee5|aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5dd**ee5**ee5|  
|5|14|<xref:System.String.Empty?displayProperty=nameWithType>|aabb2cc3dd4ee5bbcc3dd4ee5ccdd4ee5ddee5ee|  

## <a name="substituting-the-last-captured-group"></a>Ersetzen der zuletzt erfassten Gruppe  
 Die Ersetzung `$+` ersetzt die übereinstimmende Zeichenfolge durch die zuletzt erfasste Gruppe. Wenn keine erfassten Gruppen vorhanden sind oder der Wert der zuletzt erfassten Gruppe <xref:System.String.Empty?displayProperty=nameWithType>ist, hat die Ersetzung `$+` keine Auswirkungen.  
  
 Im folgenden Beispiel werden doppelte Wörter in einer Zeichenfolge identifiziert, und es wird die Ersetzung `$+` verwendet, um sie durch ein einzelnes Vorkommen des Worts zu ersetzen. Die <xref:System.Text.RegularExpressions.RegexOptions.IgnoreCase?displayProperty=nameWithType> -Option wird verwendet, um sicherzustellen, dass Wörter, die sich ausschließlich in der Groß-/Kleinschreibung unterscheiden, als Duplikate betrachtet werden.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/lastmatch1.cs#6)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/lastmatch1.vb#6)]  
  
 Das Muster für reguläre Ausdrücke `\b(\w+)\s\1\b` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(\w+)`|Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`\1`|Übereinstimmung mit der ersten erfassten Gruppe.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  

## <a name="substituting-the-entire-input-string"></a>Ersetzen der ganzen Eingabezeichenfolge  
 Die Ersetzung `$_` ersetzt die übereinstimmende Zeichenfolge durch die gesamte Eingabezeichenfolge. Das heißt, dass der übereinstimmende Text entfernt und durch die gesamte Zeichenfolge, einschließlich des übereinstimmenden Texts, ersetzt wird.  
  
 Im folgenden Beispiel werden eine oder mehrere Dezimalstellen in der Eingabezeichenfolge abgeglichen. Mithilfe der Ersetzung `$_` werden diese durch die gesamte Eingabezeichenfolge ersetzt.  
  
 [!code-csharp[Conceptual.Regex.Language.Substitutions#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.substitutions/cs/entire1.cs#7)]
 [!code-vb[Conceptual.Regex.Language.Substitutions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.substitutions/vb/entire1.vb#7)]  
  
 In diesem Beispiel enthält die Eingabezeichenfolge `"ABC123DEF456"` zwei Übereinstimmungen. Aus der folgenden Tabelle wird ersichtlich, wie die Ersetzung `$_` bewirkt, dass die Engine für reguläre Ausdrücke jede Übereinstimmung in der Eingabezeichenfolge ersetzt. Eingefügter Text wird in der Ergebnisspalte in Fettdruck angezeigt.  
  
|Match|Position|Match|Ergebniszeichenfolge|  
|-----------|--------------|-----------|-------------------|  
|1|3|123|ABC**ABC123DEF456**DEF456|  
|2|5|456|ABCABC123DEF456DEF**ABC123DEF456**|  
  
## <a name="see-also"></a>Siehe auch

- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
