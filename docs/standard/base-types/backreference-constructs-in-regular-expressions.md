---
title: Rückverweiskonstrukte in regulären .NET-Ausdrücken
description: Erfahren Sie, wie Sie wiederholte Textelemente identifizieren können, indem Sie Rückverweiskonstrukte in einem regulären Ausdruck verwenden.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- backreferences
- constructs, backreference
- .NET Framework regular expressions, backreference constructs
- regular expressions, backreference constructs
ms.assetid: 567a4b8d-0e79-49dc-8df9-f4b1aa376a2a
ms.openlocfilehash: 87c3dbde2eb2b5a19b91f34bb2b088af5c0d1827
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84290603"
---
# <a name="backreference-constructs-in-regular-expressions"></a>Rückverweiskonstrukte in regulären Ausdrücken

Rückverweise bieten eine einfache Möglichkeit, ein wiederholtes Zeichen oder eine Teilzeichenfolge innerhalb einer Zeichenfolge zu identifizieren. Wenn z.B. die Eingabezeichenfolge mehrere Vorkommen einer beliebigen Teilzeichenfolge enthält, können Sie das erste Vorkommen mit einer Erfassungsgruppe abgleichen und dann mit einem Rückverweis nachfolgende Vorkommen der Teilzeichenfolge abgleichen.

> [!NOTE]
> Eine separate Syntax wird verwendet, um auf benannte und nummerierte Erfassungsgruppen in Ersetzungszeichenfolgen zu verweisen. Weitere Informationen finden Sie unter [Ersetzungen in regulären Ausdrücken](substitutions-in-regular-expressions.md).

.NET definiert separate Sprachelemente, um auf nummerierte und benannte Erfassungsgruppen zu verweisen. Weitere Informationen zu Erfassungsgruppen finden Sie unter [Gruppierungskonstrukte in regulären Ausdrücken](grouping-constructs-in-regular-expressions.md).

## <a name="numbered-backreferences"></a>Nummerierte Rückverweise

Ein nummerierter Rückverweis verwendet die folgende Syntax:

`\` *number*

wobei *Nummer* die Ordnungsposition der Erfassungsgruppe im regulären Ausdruck ist. `\4` gleicht z.B. den Inhalt der vierten Erfassungsgruppe ab. Wenn *number* nicht im Muster eines regulären Ausdrucks definiert ist, tritt ein Analysefehler auf, und die Engine für reguläre Ausdrücke löst eine <xref:System.ArgumentException> aus. Beispielsweise ist der reguläre Ausdruck `\b(\w+)\s\1` gültig, da `(\w+)` die erste und einzige Erfassungsgruppe im Ausdruck ist. Auf der anderen Seite ist `\b(\w+)\s\2` ungültig und löst eine Argumentausnahme aus, da es keine nummerierte Erfassungsgruppe `\2` gibt. Wenn darüber hinaus *number* eine Erfassungsgruppe an einer bestimmten Ordnungsposition identifiziert, dieser Erfassungsgruppe jedoch ein anderer Name als die zugehörige Ordnungsposition zugewiesen wurde, löst der Parser für reguläre Ausdrücke ebenfalls eine <xref:System.ArgumentException> aus.

Beachten Sie die Mehrdeutigkeit zwischen oktalen Escapesequenzen (z.B. `\16`) und `\`*number*-Rückverweisen mit der gleichen Notation. Diese Mehrdeutigkeit wird wie folgt aufgelöst:

- Die Ausdrücke `\1` bis `\9` werden immer als Rückverweise und nicht als oktale Codes interpretiert.

- Wenn die erste Ziffer eines mehrziffrigen Ausdrucks 8 oder 9 ist (z.B. `\80` oder `\91`), wird der Ausdruck als Literal interpretiert.

- Ausdrücke aus `\10` und höher werden als Rückverweise betrachtet, wenn ein Rückverweis vorhanden ist, der dieser Nummer entspricht; andernfalls werden sie als oktale Codes interpretiert.

- Wenn ein regulärer Ausdruck einen Rückverweis auf eine nicht definierte Gruppennummer enthält, tritt ein Analysefehler auf, und die Engine für reguläre Ausdrücke löst eine <xref:System.ArgumentException> aus.

Wenn die Mehrdeutigkeit ein Problem ist, können Sie die Notation `\k<`*name*`>` verwenden. Sie ist eindeutig und kann nicht mit oktalen Zeichencodes verwechselt werden. Auf ähnliche Weise sind hexadezimale Codes wie z.B. `\xdd` eindeutig und können nicht mit Rückverweisen verwechselt werden.

Im folgenden Beispiel werden doppelte Wortzeichen in einer Zeichenfolge gesucht. Ein regulärer Ausdruck `(\w)\1` wird definiert, der aus den folgenden Elementen besteht.

|Element|Beschreibung|
|-------------|-----------------|
|`(\w)`|Übereinstimmung mit einem Wortzeichen und dessen Zuweisung zur ersten Erfassungsgruppe.|
|`\1`|Übereinstimmung mit dem nächsten Zeichen, das mit dem Wert der ersten Erfassungsgruppe identisch ist.|

[!code-csharp[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference1.cs#1)]
[!code-vb[RegularExpressions.Language.Backreferences#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference1.vb#1)]

## <a name="named-backreferences"></a>Benannte Rückverweise

Ein benannter Rückverweis wird mit der folgenden Syntax definiert:

`\k<` *name* `>`

oder:

`\k'` *name* `'`

wobei *Name* der Name einer Erfassungsgruppe ist, die im Muster eines regulären Ausdrucks definiert ist. Wenn *name* nicht im Muster eines regulären Ausdrucks definiert ist, tritt ein Analysefehler auf, und die Engine für reguläre Ausdrücke löst eine <xref:System.ArgumentException> aus.

Im folgenden Beispiel werden doppelte Wortzeichen in einer Zeichenfolge gesucht. Ein regulärer Ausdruck `(?<char>\w)\k<char>` wird definiert, der aus den folgenden Elementen besteht.

|Element|Beschreibung|
|-------------|-----------------|
|`(?<char>\w)`|Übereinstimmung mit einem Wortzeichen und dessen Zuweisung zu einer Erfassungsgruppe mit dem Namen `char`|
|`\k<char>`|Übereinstimmung mit dem nächsten Zeichen, das mit dem Wert der `char`-Erfassungsgruppe identisch ist|

[!code-csharp[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference2.cs#2)]
[!code-vb[RegularExpressions.Language.Backreferences#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference2.vb#2)]

## <a name="named-numeric-backreferences"></a>Benannte numerische Rückverweise

In einem benannten Rückverweis mit `\k` kann *name* auch die Zeichenfolgendarstellung einer Zahl sein. Im folgenden Beispiel werden mit dem regulären Ausdruck `(?<2>\w)\k<2>` doppelte Wortzeichen in einer Zeichenfolge gesucht. In diesem Fall definiert das Beispiel eine Erfassungsgruppe, die explizit als „2“ benannt wurde. Der Rückverweis wurde entsprechend ebenfalls „2“ genannt.

[!code-csharp[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference3.cs#3)]
[!code-vb[RegularExpressions.Language.Backreferences#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference3.vb#3)]

Wenn *name* die Zeichenfolgendarstellung einer Zahl ist und keine Erfassungsgruppe diesen Namen trägt, ist `\k<`*name*`>` das Gleiche wie der Rückverweis `\`*number*, wobei *number* die Ordnungsposition der Erfassung ist. Im folgenden Beispiel gibt es eine einzige Erfassungsgruppe namens `char`. Das Rückverweiskonstrukt referenziert die Gruppe als `\k<1>`. Wie die Ausgabe des Beispiels zeigt, ist der Aufruf von <xref:System.Text.RegularExpressions.Regex.IsMatch%2A?displayProperty=nameWithType> erfolgreich, weil `char` die erste Erfassungsgruppe ist.

[!code-csharp[Ordinal.Backreference](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference6.cs)]
[!code-vb[Ordinal.BackReference](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference6.vb)]

Wenn jedoch *name* die Zeichenfolgendarstellung einer Zahl ist und der Erfassungsgruppe an dieser Position explizit ein numerischer Name zugewiesen wurde, kann der Parser für reguläre Ausdrücke die Erfassungsgruppe nicht anhand ihrer Ordnungsposition identifizieren. Stattdessen wird <xref:System.ArgumentException> ausgelöst. Die einzige Erfassungsgruppe im folgenden Beispiel ist „2“. Da das `\k`-Konstrukt verwendet wird, um einen Rückverweis namens „1“ zu definieren, kann der Parser für reguläre Ausdrücke die erste Erfassungsgruppe nicht identifizieren und löst eine Ausnahme aus.

[!code-csharp[Ordinal.Backreference](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference7.cs)]
[!code-vb[Ordinal.BackReference](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference7.vb)]

## <a name="what-backreferences-match"></a>Übereinstimmende Rückverweise

Ein Rückverweis bezieht sich auf die aktuellste Definition einer Gruppe (beim Abgleichen von links nach rechts die am weitesten links befindliche Definition). Wenn eine Gruppe mehrere Erfassungen durchführt, bezieht sich ein Rückverweis auf die aktuellste Erfassung.

Das folgende Beispiel enthält ein Muster für reguläre Ausdrücke, `(?<1>a)(?<1>\1b)*`, das die Gruppe namens „\1“ neu definiert. Die folgende Tabelle beschreibt jedes Muster im regulären Ausdruck.

|Muster|Beschreibung|
|-------------|-----------------|
|`(?<1>a)`|Übereinstimmung mit dem Zeichen „a“ und Zuweisen des Ergebnisses zur Erfassungsgruppe `1`|
|`(?<1>\1b)*`|Übereinstimmung mit null oder einem Vorkommen der Gruppe `1` zusammen mit einem „b“ und Zuweisen des Ergebnisses zur Erfassungsgruppe `1`|

[!code-csharp[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference4.cs#4)]
[!code-vb[RegularExpressions.Language.Backreferences#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference4.vb#4)]

Beim Vergleich des regulären Ausdrucks mit der Eingabezeichenfolge („aababb“) führt die Engine für reguläre Ausdrücke die folgenden Vorgänge aus:

1. Begonnen wird am Anfang der Zeichenfolge, und „a“ wird erfolgreich mit dem Ausdruck `(?<1>a)` abgeglichen. Der Wert der Gruppe `1` ist nun „a“.

2. Es wird zum zweiten Zeichen gewechselt, und die Zeichenfolge „ab“ wird erfolgreich mit dem Ausdruck `\1b` bzw. „ab“ abgeglichen. Anschließend wird `\1` das Ergebnis „ab“ zugewiesen.

3. Es wird zum vierten Zeichen gewechselt. Der Ausdruck `(?<1>\1b)*` muss nullmal oder mehrfach abgeglichen werden, damit er der Zeichenfolge „abb“ mit dem Ausdruck `\1b` entspricht. Das Ergebnis „abb“ wird wieder `\1` zugewiesen.

In diesem Beispiel ist `*` ein Schleifenquantifizierer – er wird wiederholt ausgewertet, bis die Engine für reguläre Ausdrücke keine Entsprechung für das Muster finden kann, das sie definiert. Quantifizierer, die in Schleifen durchlaufen werden, löschen keine Gruppendefinitionen.

Wurden durch eine Gruppe keine Teilzeichenfolgen gefunden, ist der Rückverweis auf diese Gruppe nicht definiert und führt niemals zu einer Übereinstimmung. Dies wird durch das Muster des regulären Ausdrucks `\b(\p{Lu}{2})(\d{2})?(\p{Lu}{2})\b` veranschaulicht, das folgendermaßen definiert ist:

|Muster|Beschreibung|
|-------------|-----------------|
|`\b`|Beginnt den Vergleich an einer Wortgrenze.|
|`(\p{Lu}{2})`|Übereinstimmung mit zwei Großbuchstaben. Dies ist die erste Erfassungsgruppe.|
|`(\d{2})?`|Übereinstimmung mit null oder einem Vorkommen von zwei Dezimalziffern. Dies ist die zweite Erfassungsgruppe.|
|`(\p{Lu}{2})`|Übereinstimmung mit zwei Großbuchstaben. Dies ist die dritte Erfassungsgruppe.|
|`\b`|Beendet den Vergleich an einer Wortgrenze.|

Eine Eingabezeichenfolge kann auch dann mit diesem regulären Ausdruck übereinstimmen, wenn die von der zweiten Erfassungsgruppe definierten zwei Dezimalziffern nicht vorhanden sind. Das folgende Beispiel zeigt, dass trotz Übereinstimmung eine leere Erfassungsgruppe zwischen zwei erfolgreichen Erfassungsgruppen gefunden wird.

[!code-csharp[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/csharp/VS_Snippets_CLR/regularexpressions.language.backreferences/cs/backreference5.cs#5)]
[!code-vb[RegularExpressions.Language.Backreferences#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/regularexpressions.language.backreferences/vb/backreference5.vb#5)]

## <a name="see-also"></a>Weitere Informationen

- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](regular-expression-language-quick-reference.md)
