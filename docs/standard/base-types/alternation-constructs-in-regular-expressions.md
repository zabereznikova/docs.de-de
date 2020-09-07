---
title: Alternierungskonstrukte in regulären .NET-Ausdrücken
description: Erfahren Sie, wie Sie Alternierungskonstrukte für den bedingten Abgleich in regulären Ausdrücken verwenden können.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- either/or matching
- alternative matching patterns
- regular expressions, alternation constructs
- alternation constructs
- optional matching patterns
- constructs, alternation
- .NET Framework regular expressions, alternation constructs
ms.assetid: 071e22e9-fbb0-4ecf-add1-8d2424f9f2d1
ms.openlocfilehash: 506c1cdeb577452628d67ab00df20dd30881f406
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495433"
---
# <a name="alternation-constructs-in-regular-expressions"></a>Alternierungskonstrukte in regulären Ausdrücken

Alternierungskonstrukte ändern einen regulären Ausdruck, um Entweder-Oder-Vergleiche oder eine bedingte Übereinstimmung zuzulassen. .NET unterstützt drei Alternierungskonstrukte:

- [Musterabgleich mit &#124;](#Either_Or)
- [Bedingte Übereinstimmung mit (?(Ausdruck)ja&#124;nein)](#Conditional_Expr)
- [Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe](#Conditional_Group)

<a name="Either_Or"></a>
## <a name="pattern-matching-with-124"></a>Musterabgleich mit &#124;

Sie können das vertikale Balkenzeichen (`|`) für Vergleiche mit einem oder mehreren aus einer Reihe von Mustern verwenden, wobei das `|`-Zeichen als Trennzeichen für die einzelnen Muster dient.

Wie bei der positiven Zeichenklasse kann das `|` -Zeichen für Vergleiche mit jedem beliebigen Zeichen aus einer Reihe einzelner Zeichen verwendet werden. Im folgenden Beispiel wird sowohl eine positive Zeichenklasse als auch ein Entweder-Oder-Mustervergleich mithilfe des `|` -Zeichens verwendet, um Vorkommen der Wörter „gray“ oder „grau“ in einer Zeichenfolge zu finden. In diesem Fall ergibt das `|` -Zeichen einen regulären Ausdruck, der eine ausführlichere Ausgabe bewirkt.

[!code-csharp[RegularExpressions.Language.Alternation#1](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation1.cs#1)]
[!code-vb[RegularExpressions.Language.Alternation#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation1.vb#1)]

Der reguläre Ausdruck `\bgr(a|e)y\b`, der das `|`-Zeichen verwendet, wird entsprechend der Darstellung in der folgenden Tabelle interpretiert:

|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`gr`|Übereinstimmung mit den Zeichen "gr".|  
|<code>(a&#124;e)</code>|Übereinstimmung mit entweder "a" oder "e".|  
|`y\b`|Übereinstimmung mit "y" an einer Wortgrenze.|  

Das `|`-Zeichen kann auch verwendet werden, um einen Entweder-Oder-Vergleich mit mehreren Zeichen oder Teilausdrücken durchzuführen, wobei eine beliebige Kombination von Zeichenliteralen und Sprachelementen für reguläre Ausdrücke enthalten sein kann. (Die Zeichenklasse stellt diese Funktionalität nicht bereit.) Im folgenden Beispiel wird das `|`-Zeichen verwendet, um entweder eine Sozialversicherungsnummer in den USA, also eine neunstellige Zahl mit dem Format *ddd*-*dd*-*dddd*, oder eine Identifikationsnummer des Arbeitgebers in den USA (EIN, Employer Identification Number), also eine neunstellige Zahl mit dem Format *dd*-*ddddddd* zu extrahieren.

[!code-csharp[RegularExpressions.Language.Alternation#2](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation2.cs#2)]
[!code-vb[RegularExpressions.Language.Alternation#2](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation2.vb#2)]  

Der reguläre Ausdruck `\b(\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|<code>(\d{2}-\d{7}&#124;\d{3}-\d{2}-\d{4})</code>|Eine der folgenden Varianten muss übereinstimmen: zwei Dezimalstellen gefolgt von einem Bindestrich gefolgt von sieben Dezimalstellen; oder drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen.|  
|`\b`|Der Vergleich endet an einer Wortgrenze.|  
  
<a name="Conditional_Expr"></a>
## <a name="conditional-matching-with-an-expression"></a>Bedingte Übereinstimmung mit einem Ausdruck

Dieses Sprachelement versucht, mit einem der zwei Muster übereinzustimmen, abhängig davon, ob es ein ursprüngliches Muster zuordnen kann. Die Syntax lautet:  

`(?(` *expression* `)` *yes* `|` *no* `)`

wobei *expression* das ursprüngliche zu enstprechende Muster ist. *yes* ist das entsprechende Muster, wenn *expression* zugeordnet ist, und *no* ist das entsprechende optionale Muster, wenn *expression* nicht übereinstimmt. Die Engine für reguläre Ausdrücke behandelt *Ausdruck* als Assertion mit einer Breite von Null, das heißt, dass die Engine für reguläre Ausdrücke im Eingabestream nicht weitergeführt wird, nachdem sie *Ausdruck* auswertet. Daher entspricht dieses Konstrukt Folgendem:

`(?(?=` *expression* `)` *yes* `|` *no* `)`

wobei `(?=`*Ausdruck*`)` ein Assertionskonstrukt mit einer Breite von null ist. (Weitere Informationen finden Sie unter [Gruppierungskonstrukte](grouping-constructs-in-regular-expressions.md).) Da die Engine für reguläre Ausdrücke *Ausdruck* als Anker (eine Assertion mit einer Breite von null) interpretiert, muss *Ausdruck* entweder eine Assertion mit einer Breite von null (weitere Informationen finden Sie unter [Anker](anchors-in-regular-expressions.md)) oder ein Teilausdruck sein, der auch in *a* enthalten ist. Andernfalls kann das Muster *yes* nicht zugeordnet werden.  
  
> [!NOTE]
> Wenn *expression* eine benannte oder nummerierte Erfassungsgruppe ist, wird das Alternierungskonstrukt als Erfassungstest interpretiert. Weitere Informationen finden Sie im nächsten Abschnitt [Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe](#Conditional_Group). Das heißt, dass die Engine für reguläre Ausdrücke nicht versucht, mit der erfassten Teilzeichenfolge übereinzustimmen. Stattdessen wird das Vorhandensein oder Fehlen der Gruppe getestet.  
  
Das folgende Beispiel ist eine Abwandlung des Beispiels, das im Abschnitt [Entweder-Oder-Musterabgleich mit &#124;](#Either_Or) vorhanden ist. Es wird die bedingte Übereinstimmung verwendet, um zu ermitteln, ob die ersten drei Zeichen nach einer Wortgrenze zwei Ziffern gefolgt von einem Bindestrich sind. Wenn dies der Fall ist, wird eine Übereinstimmung mit einer Identifikationsnummer des Arbeitgebers in den USA versucht. Wenn dies nicht der Fall ist, wird eine Übereinstimmung mit einer Sozialversicherungsnummer in den USA versucht.

[!code-csharp[RegularExpressions.Language.Alternation#3](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation3.cs#3)]
[!code-vb[RegularExpressions.Language.Alternation#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation3.vb#3)]

Das Muster für reguläre Ausdrücke `\b(?(\d{2}-)\d{2}-\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:

|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`(?(\d{2}-)`|Bestimmen, ob die nächsten drei Zeichen aus zwei Ziffern gefolgt von einem Bindestrich bestehen.|  
|`\d{2}-\d{7}`|Wenn das vorherige Muster übereinstimmt, stimmen zwei Ziffern gefolgt von einem Bindestrich gefolgt von sieben Ziffern überein.|  
|`\d{3}-\d{2}-\d{4}`|Wenn das vorherige Muster nicht übereinstimmt, stimmen drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen überein.|  
|`\b`|Übereinstimmung mit einer Wortgrenze.|  

<a name="Conditional_Group"></a>
## <a name="conditional-matching-based-on-a-valid-captured-group"></a>Bedingte Übereinstimmung auf Grundlage einer gültigen erfassten Gruppe

Dieses Sprachelement versucht, mit einem der zwei Muster übereinzustimmen, abhängig davon, ob es mit einer angegebenen Erfassungsgruppe übereingestimmt hat. Die Syntax lautet:

`(?(` *name* `)` *yes* `|` *no* `)`

oder

`(?(` *number* `)` *yes* `|` *no* `)`

, wobei *name* der Name und *number* die Nummer einer Erfassungsgruppe ist. *yes* ist der zu übereinstimmende Ausdruck, wenn *name* oder *number* eine Übereinstimmung aufweist, und *no* ist der optionale zu übereinstimmende Ausdruck, wenn dies nicht der Fall ist.

Wenn *name* nicht dem Namen einer Erfassungsgruppe entspricht, die im Muster des regulären Ausdrucks verwendet wird, wird das Alternierungskonstrukt, wie im vorherigen Abschnitt erläutert, als Ausdruckstest interpretiert. In der Regel bedeutet dies, dass *expression*`false`ergibt. Wenn *number* keiner nummerierten Erfassungsgruppe entspricht, die im Muster des regulären Ausdrucks verwendet wird, löst die Engine für reguläre Ausdrücke eine <xref:System.ArgumentException> aus.

Das folgende Beispiel ist eine Abwandlung des Beispiels, das im Abschnitt [Entweder-Oder-Musterabgleich mit &#124;](#Either_Or) vorhanden ist. Es wird eine Erfassungsgruppe mit dem Namen `n2` verwendet, die aus zwei Ziffern gefolgt von einem Bindestrich besteht. Das Alternierungskonstrukt testet, ob diese Erfassungsgruppe in der Eingabezeichenfolge abgeglichen wurde. Wenn dies der Fall ist, versucht das Alternierungskonstrukt, mit den letzten sieben Ziffern einer neunstelligen Identifikationsnummer des Arbeitgebers in den USA versucht. Wenn dies nicht der Fall ist, versucht es, mit einer neunstelligen Sozialversicherungsnummer in den USA versucht.

[!code-csharp[RegularExpressions.Language.Alternation#4](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation4.cs#4)]
[!code-vb[RegularExpressions.Language.Alternation#4](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation4.vb#4)]

Das Muster für reguläre Ausdrücke `\b(?<n2>\d{2}-)?(?(n2)\d{7}|\d{3}-\d{2}-\d{4})\b` wird entsprechend der folgenden Tabelle interpretiert:

|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`(?<n2>\d{2}-)?`|Entspricht 0 (Null) oder einem Vorkommen von zwei Ziffern gefolgt von einem Bindestrich. Geben Sie für die Erfassungsgruppe `n2` als Namen an.|  
|`(?(n2)`|Prüfen, ob `n2` in der Eingabezeichenfolge abgeglichen wurde.|  
|`\d{7}`|Wenn `n2` abgeglichen wurde, stimmen sieben Dezimalstellen überein.|  
|<code>&#124;\d{3}-\d{2}-\d{4}</code>|Wenn `n2` nicht abgeglichen wurde, stimmen drei Dezimalstellen, ein Bindestrich, zwei Dezimalstellen, ein weiterer Bindestrich und vier Dezimalstellen überein.|  
|`\b`|Übereinstimmung mit einer Wortgrenze.|  

Eine Variante dieses Beispiels, die eine nummerierte Gruppe statt einer benannten Gruppe verwendet, wird im folgenden Beispiel gezeigt. Das entsprechende Muster des regulären Ausdrucks lautet `\b(\d{2}-)?(?(1)\d{7}|\d{3}-\d{2}-\d{4})\b`.

[!code-csharp[RegularExpressions.Language.Alternation#5](~/samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.alternation/cs/alternation5.cs#5)]
[!code-vb[RegularExpressions.Language.Alternation#5](~/samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.alternation/vb/alternation5.vb#5)]

## <a name="see-also"></a>Siehe auch

- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md)
