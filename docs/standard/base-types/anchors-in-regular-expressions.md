---
title: Anchor in regulären .NET-Ausdrücken
description: Erfahren Sie, wie Sie Anchor in Mustern für reguläre Ausdrücke verwenden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- atomic zero-width assertions
- regular expressions, anchors
- regular expressions, atomic zero-width assertions
- anchors, in regular expressions
- metacharacters, atomic zero-width assertions
- metacharacters, anchors
- .NET regular expressions, anchors
- .NET regular expressions, atomic zero-width assertions
ms.assetid: 336391f6-2614-499b-8b1b-07a6837108a7
ms.openlocfilehash: a6330eebbc69b9a3877a99a4373810d5a124c570
ms.sourcegitcommit: 4a938327bad8b2e20cabd0f46a9dc50882596f13
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "92889165"
---
# <a name="anchors-in-regular-expressions"></a>Anchor in regulären Ausdrücken
Anker, auch als atomische Nullbreitenassertionen bezeichnet, geben eine Position in der Zeichenfolge an, an der eine Übereinstimmung auftreten muss. Wenn Sie im Suchausdruck einen Anchor verwenden, durchsucht die Engine für reguläre Ausdrücke nicht die Zeichenfolge oder durchläuft Zeichen, sondern sucht nur an der angegebenen Position nach einer Übereinstimmung. Beispielsweise gibt `^` an, dass die Übereinstimmung am Anfang einer Zeile oder Zeichenfolge beginnen muss. Daher stimmt der reguläre Ausdruck `^http:` nur mit "http:" überein, wenn dies am Anfang einer Zeile steht. In der folgenden Tabelle werden die von den regulären .NET-Ausdrücken unterstützten Anchor aufgeführt.  
  
|Anchor|Beschreibung|  
|------------|-----------------|  
|`^`|Die Übereinstimmung muss standardmäßig zu Beginn der Zeichenfolge stattfinden. Im Mehrzeilenmodus muss sie zu Beginn der Zeile erfolgen. Weitere Informationen finden Sie unter [Anfang der Zeichenfolge oder Zeile](#start-of-string-or-line-).|  
|`$`|Die Übereinstimmung muss standardmäßig am Ende der Zeichenfolge oder vor `\n` am Ende der Zeichenfolge stattfinden. Im Mehrzeilenmodus muss sie am Ende der Zeile oder vor `\n` am Ende der Zeile erfolgen. Weitere Informationen finden Sie unter [Ende der Zeichenfolge oder Zeile](#end-of-string-or-line-).|  
|`\A`|Die Übereinstimmung darf nur am Anfang der Zeichenfolge vorliegen (mehrere Zeilen werden nicht unterstützt). Weitere Informationen finden Sie unter [Nur Anfang der Zeichenfolge](#start-of-string-only-a).|  
|`\Z`|Der Vergleich muss am Ende der Zeichenfolge oder vor `\n` am Ende der Zeichenfolge erfolgen. Weitere Informationen finden Sie unter [Ende der Zeichenfolge oder vor dem abschließenden Zeilenumbruch](#end-of-string-or-before-ending-newline-z).|  
|`\z`|Die Übereinstimmung darf nur am Ende der Zeichenfolge vorliegen. Weitere Informationen finden Sie unter [Nur Ende der Zeichenfolge](#end-of-string-only-z).|  
|`\G`|Die Übereinstimmung muss an dem Punkt beginnen, an dem die vorherige Übereinstimmung endete. Weitere Informationen finden Sie unter [Aufeinander folgende Übereinstimmungen](#contiguous-matches-g).|  
|`\b`|Die Übereinstimmung muss an einer Wortgrenze vorliegen. Weitere Informationen finden Sie unter [Wortgrenze](#word-boundary-b).|  
|`\B`|Die Übereinstimmung darf nicht an einer Wortgrenze vorliegen. Weitere Informationen finden Sie unter [Nicht-Wortgrenze](#non-word-boundary-b).|  

## <a name="start-of-string-or-line-"></a>Anfang der Zeichenfolge oder Zeile: ^  
 Der `^`-Anchor gibt standardmäßig an, dass das folgende Muster an der ersten Zeichenposition der Zeichenfolge beginnen muss. Wenn Sie `^` mit der <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>-Option (siehe [Optionen für reguläre Ausdrücke](regular-expression-options.md)) verwenden, muss die Übereinstimmung am Anfang jeder Zeile vorliegen.  
  
 Im folgenden Beispiel wird der `^` -Anchor in einem regulären Ausdruck verwendet, der Informationen zu den Jahren extrahiert, in denen es bestimmte professionelle Baseballteams gab. Im Beispiel werden zwei Überladungen der <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> -Methode aufgerufen:  
  
- Der Aufruf der <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29> -Überladung sucht nur die erste Teilzeichenfolge in der Eingabezeichenfolge, die mit dem Muster des regulären Ausdrucks übereinstimmt.  
  
- Der Aufruf der <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29> -Überladung sucht bei Festlegung des `options` -Parameters auf <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> alle fünf Teilzeichenfolgen.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/startofstring1.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/startofstring1.vb#1)]  
  
 Das Muster für reguläre Ausdrücke `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+` wird entsprechend der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`^`|Suchen Sie nach einer Übereinstimmung am Anfang der Eingabezeichenfolge (oder am Anfang der Zeile, wenn die Methode mit der <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> -Option aufgerufen wird).|  
|`((\w+(\s?)){2,}`|Suchen Sie nach einer Übereinstimmung mit mindestens einem Wortzeichen, auf das mindestens zwei Mal eine 0 (Null) oder ein Leerzeichen folgt. Dies ist die erste Erfassungsgruppe. Dieser Ausdruck definiert auch eine zweite und dritte Erfassungsgruppe: Die zweite Gruppe enthält erfasste Wörter und die dritte erfasste Leerzeichen.|  
|`,\s`|Suchen Sie nach einer Übereinstimmung mit einem Komma gefolgt von einem Leerzeichen.|  
|`(\w+\s\w+)`|Suchen Sie nach einer Übereinstimmung mit einem oder mehreren Wortzeichen gefolgt von mindestens einem Wortzeichen. Dies ist die vierte Erfassungsgruppe.|  
|`,`|Entsprechung für ein Komma finden.|  
|`\s\d{4}`|Suchen Sie nach einer Übereinstimmung mit einem von vier Dezimalzahlen gefolgten Leerzeichen.|  
|<code>(-(\d{4}&#124;present))?</code>|Suchen Sie nach einer Übereinstimmung mit 0 (Null) oder einem Bindestrich gefolgt von vier Dezimalzahlen oder der Zeichenfolge "present". Dies ist die sechste Erfassungsgruppe. Diese Gruppe enthält auch eine siebte Erfassungsgruppe.|  
|`,?`|Suchen Sie nach einer Übereinstimmung mit 0 (null) oder einem Komma.|  
|<code>(\s\d{4}(-(\d{4}&#124;present))?,?)+</code>|Suchen Sie nach einer Übereinstimmung mit mindestens einem Vorkommen der folgenden Elemente: ein Leerzeichen, vier Dezimalzahlen, 0 (Null) oder ein Bindestrich gefolgt von vier Dezimalzahlen oder der Zeichenfolge "present" sowie 0 (Null) oder ein Komma. Dies ist die fünfte Erfassungsgruppe.|

## <a name="end-of-string-or-line-"></a>Ende der Zeichenfolge oder Zeile: $  
 Der `$` -Anchor gibt an, dass das vorangehende Muster am Ende der Eingabezeichenfolge oder vor `\n` am Ende der Eingabezeichenfolge vorliegen muss.  
  
 Wenn Sie `$` mit der <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> -Option verwenden, kann die Übereinstimmung auch am Ende einer Zeile vorliegen. Beachten Sie, dass `$` mit `\n` übereinstimmt, nicht jedoch mit `\r\n` (der Kombination aus Wagenrücklauf- und Zeilenumbruchzeichen oder CR/LF). Zum Suchen einer Übereinstimmung mit der CR/LF-Zeichenkombination schließen Sie `\r?$` in das Muster des regulären Ausdrucks ein.  
  
 Im folgenden Beispiel wird der `$` -Anchor zum Muster des regulären Ausdrucks hinzugefügt, der im Beispiel im Abschnitt [Anfang der Zeichenfolge oder Zeile](#start-of-string-or-line-) verwendet wurde. Bei Verwendung mit der ursprünglichen Eingabezeichenfolge von fünf Textzeilen wird von der <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29?displayProperty=nameWithType> -Methode keine Übereinstimmung gefunden, da das Ende der ersten Zeile nicht mit dem `$` -Muster übereinstimmt. Wenn die ursprüngliche Eingabezeichenfolge in ein Zeichenfolgenarray geteilt wird, findet die <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%29?displayProperty=nameWithType> -Methode eine Übereinstimmung mit jeder der fünf Zeilen. Wenn die <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> -Methode mit dem auf `options` festgelegten <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType>-Parameter aufgerufen wird, werden keine Übereinstimmungen gefunden, da das Wagenrücklaufelement (\u+000D) nicht Teil des Musters des regulären Ausdrucks ist. Wenn das Muster des regulären Ausdrucks jedoch geändert wird, indem `$` durch `\r?$`ersetzt wird, ergibt der Aufruf der <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> -Methode, sofern der `options` -Parameter auf <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> festgelegt ist, wieder fünf Übereinstimmungen.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring1.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring1.vb#2)]

## <a name="start-of-string-only-a"></a>Nur Anfang der Zeichenfolge: \A  
 Der `\A` -Anchor gibt an, dass eine Übereinstimmung am Anfang der Eingabezeichenfolge vorliegen muss. Dies ist mit dem `^` -Anchor identisch, jedoch wird die `\A` -Option von <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> ignoriert. Daher kann hiermit in einer mehrzeiligen Eingabezeichenfolge nur eine Übereinstimmung nur am Anfang der ersten Zeile gesucht werden.  
  
 Das folgende Beispiel ähnelt den Beispielen für den `^` -Anchor und den `$` -Anchor. Der `\A` -Anchor wird in einem regulären Ausdruck verwendet, der Informationen zu den Jahren extrahiert, in denen es bestimmte professionelle Baseballteams gab. Die Eingabezeichenfolge weist fünf Zeilen auf. Der Aufruf der <xref:System.Text.RegularExpressions.Regex.Matches%28System.String%2CSystem.String%2CSystem.Text.RegularExpressions.RegexOptions%29?displayProperty=nameWithType> -Methode sucht nur die erste Teilzeichenfolge in der Eingabezeichenfolge, die mit dem Muster des regulären Ausdrucks übereinstimmt. Wie im Beispiel dargestellt, hat die <xref:System.Text.RegularExpressions.RegexOptions.Multiline> -Option keine Auswirkungen.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/startofstring2.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/startofstring2.vb#3)]

## <a name="end-of-string-or-before-ending-newline-z"></a>Ende der Zeichenfolge oder vor dem abschließenden Zeilenumbruch: \Z  
 Der `\Z` -Anchor gibt an, dass eine Übereinstimmung am Ende der Eingabezeichenfolge oder vor `\n` am Ende der Eingabezeichenfolge vorliegen muss. Dies ist mit dem `$` -Anchor identisch, jedoch wird die `\Z` -Option von <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> ignoriert. Daher kann hiermit in einer mehrzeiligen Zeichenfolge nur nach einer Übereinstimmung mit dem Ende der letzten Zeile oder der letzten Zeile vor `\n`gesucht werden.  
  
 Beachten Sie, dass `\Z` mit `\n` , aber nicht mit `\r\n` übereinstimmt (der CR/LF-Zeichenkombination). Zum Suchen einer Übereinstimmung mit CR/LF schließen Sie `\r?\Z` in das Muster des regulären Ausdrucks ein.  
  
 Im folgenden Beispiel wird der `\Z` -Anchor in einem regulären Ausdruck verwendet, der ähnlich wie das Beispiel aus dem Abschnitt [Anfang der Zeichenfolge oder Zeile](#start-of-string-or-line-) Informationen zu den Jahren extrahiert, in denen es bestimmte professionelle Baseballteams gab. Der Teilausdruck `\r?\Z` im regulären Ausdruck `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\Z` stimmt sowohl mit dem Ende einer Zeichenfolge als auch mit einer Zeichenfolge überein, die mit `\n` oder `\r\n`endet. Folglich stimmt jedes Element im Array mit dem Muster des regulären Ausdrucks überein.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring2.cs#4)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring2.vb#4)]

## <a name="end-of-string-only-z"></a>Nur Ende der Zeichenfolge: \z  
 Der `\z` -Anchor gibt an, dass eine Übereinstimmung am Ende der Eingabezeichenfolge vorliegen muss. Wie das `$` -Sprachelement ignoriert `\z` die <xref:System.Text.RegularExpressions.RegexOptions.Multiline?displayProperty=nameWithType> -Option. Im Gegensatz zum `\Z` -Sprachelement stimmt `\z` nicht mit einem `\n` -Zeichen am Ende einer Zeichenfolge überein. Daher kann hiermit nur eine Übereinstimmung mit der letzten Zeile der Eingabezeichenfolge gesucht werden.  
  
 Im folgenden Beispiel wird der `\z` -Anchor in einem regulären Ausdruck verwendet, der ansonsten mit dem Beispiel aus dem vorherigen Abschnitt übereinstimmt und Informationen zu den Jahren extrahiert, in denen es bestimmte professionelle Baseballteams gab. Im Beispiel wird versucht, eine Übereinstimmung mit dem Muster eines regulären Ausdrucks `^((\w+(\s?)){2,}),\s(\w+\s\w+),(\s\d{4}(-(\d{4}|present))?,?)+\r?\z`für jedes der fünf Elemente in einem Zeichenfolgenarray zu finden. Zwei der Zeichenfolgen enden mit Wagenrücklauf- und Zeilenvorschubzeichen, eine endet mit einem Zeilenvorschubzeichen, und zwei enden weder mit einem Wagenrücklauf- noch mit einem Zeilenvorschubzeichen. Wie die Ausgabe ergibt, stimmen nur die Zeichenfolgen ohne Wagenrücklauf oder Zeilenvorschub mit dem Muster überein.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/endofstring3.cs#5)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/endofstring3.vb#5)]

## <a name="contiguous-matches-g"></a>Aufeinander folgende Übereinstimmungen: \G  
 Der `\G` -Anchor gibt an, dass eine Übereinstimmung an dem Punkt vorliegen muss, an dem die vorherige Übereinstimmung endet. Wenn Sie diesen Anchor mit der <xref:System.Text.RegularExpressions.Regex.Matches%2A?displayProperty=nameWithType> -Methode oder <xref:System.Text.RegularExpressions.Match.NextMatch%2A?displayProperty=nameWithType> -Methode verwenden, wird damit sichergestellt, dass alle Übereinstimmungen zusammenhängend sind.  
  
 Im folgenden Beispiel werden mithilfe eines regulären Ausdrucks die Namen von Nagetierspezies aus einer durch Trennzeichen getrennten Zeichenfolge extrahiert.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/contiguous1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/contiguous1.vb#6)]  
  
 Der reguläre Ausdruck `\G(\w+\s?\w*),?` wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\G`|Beginnt die Übereinstimmung am Ende der vorherigen.|  
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|  
|`\s?`|Übereinstimmung mit 0 (Null) oder einem Leerzeichen.|  
|`\w*`|Übereinstimmung mit keinem oder mehreren Wortzeichen.|  
|`(\w+\s?\w*)`|Übereinstimmung mit mindestens einem Wortzeichen gefolgt von 0 (Null) oder einem Leerzeichen, gefolgt von 0 (Null) oder weiteren Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|`,?`|Übereinstimmung mit 0 (Null) oder einem Literal-Kommazeichen.|

## <a name="word-boundary-b"></a>Wortgrenze: \b  
 Der `\b` -Anchor gibt an, dass die Übereinstimmung an einer Grenze zwischen einem Wortzeichen (dem `\w` -Sprachelement) und einem Nicht-Wortzeichen (dem `\W` -Sprachelement) vorliegen muss. Wortzeichen bestehen aus alphanumerischen Zeichen und Unterstrichen. Bei Nicht-Wortzeichen handelt es sich um alle Zeichen, die weder alphanumerisch noch Unterstriche sind. (Weitere Informationen finden Sie unter [Zeichenklassen in regulären Ausdrücken](character-classes-in-regular-expressions.md).) Die Übereinstimmung kann auch an einer Wortgrenze am Anfang oder Ende der Zeichenfolge vorliegen.  
  
 Der `\b` -Anchor wird häufig verwendet, um sicherzustellen, dass ein Teilausdruck statt nur mit Anfang oder Ende mit einem ganzen Wort übereinstimmt. Im folgenden Beispiel wird die Verwendung des regulären Ausdrucks `\bare\w*\b` veranschaulicht. Der Ausdruck stimmt mit jedem Wort überein, das mit der Teilzeichenfolge "are" beginnt. Die Ausgabe des Beispiels veranschaulicht auch, dass `\b` sowohl mit dem Anfang als auch dem Ende der Eingabezeichenfolge übereinstimmt.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/word1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/word1.vb#7)]  
  
 Das Muster für reguläre Ausdrücke wird entsprechend der folgenden Tabelle interpretiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`are`|Übereinstimmung mit der Teilzeichenfolge "are".|  
|`\w*`|Übereinstimmung mit keinem oder mehreren Wortzeichen.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  

## <a name="non-word-boundary-b"></a>Nicht-Wortgrenze: \B  
 Der `\B` -Anchor gibt an, dass die Übereinstimmung nicht an einer Wortgrenze vorliegen darf. Dies ist das Gegenteil des `\b` -Anchor.  
  
 Im folgenden Beispiel wird der `\B` -Anchor verwendet, um nach Vorkommen der Teilzeichenfolge "qu" in einem Wort zu suchen. Das Muster des regulären Ausdrucks `\Bqu\w+` stimmt mit einer Teilzeichenfolge überein, die mit "qu" beginnt, nicht der Wortbeginn ist und bis zum Ende des Worts reicht.  
  
 [!code-csharp[Conceptual.RegEx.Language.Assertions#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.assertions/cs/nonword1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.Assertions#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.assertions/vb/nonword1.vb#8)]  
  
 Das Muster für reguläre Ausdrücke wird entsprechend der folgenden Tabelle interpretiert.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\B`|Übereinstimmung beginnt nicht an einer Wortgrenze.|  
|`qu`|Übereinstimmung mit der Teilzeichenfolge "qu".|  
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|  
  
## <a name="see-also"></a>Siehe auch

- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md)
- [Optionen für reguläre Ausdrücke](regular-expression-options.md)
