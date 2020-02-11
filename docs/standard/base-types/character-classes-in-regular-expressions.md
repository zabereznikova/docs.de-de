---
title: Zeichenklassen in regulären .NET-Ausdrücken
description: Erfahren Sie, wie Sie mit Zeichenklassen einen Zeichensatz in regulären .NET-Ausdrücken darstellen.
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- character classes
- regular expressions, character classes
- characters, matching syntax
- .NET Framework regular expressions, character classes
ms.assetid: 0f8bffab-ee0d-4e0e-9a96-2b4a252bb7e4
ms.openlocfilehash: 047d0ea7b3783f8cf45afde2a15470adda94cd6e
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2020
ms.locfileid: "77095046"
---
# <a name="character-classes-in-regular-expressions"></a>Zeichenklassen in regulären Ausdrücken

Eine Zeichenklasse definiert einen Satz von Zeichen, von denen jedes in einer Eingabezeichenfolge enthalten sein kann, damit eine Übereinstimmung vorliegt. Die Sprache für reguläre Ausdrücke in .NET unterstützt die folgenden Zeichenklassen:  
  
- Positive Zeichengruppen. Ein Zeichen in der Eingabezeichenfolge muss mit einem Zeichen in einem angegebenen Zeichensatz übereinstimmen. Weitere Informationen finden Sie unter [Positive Zeichengruppe](#PositiveGroup).  
  
- Negative Zeichengruppen. Ein Zeichen in der Eingabezeichenfolge darf nicht mit einem Zeichen in einem angegebenen Zeichensatz übereinstimmen. Weitere Informationen finden Sie unter [Negative Zeichengruppe](#NegativeGroup).  
  
- Jedes Zeichen. Beim `.`-Zeichen (Punkt) in einem regulären Ausdruck handelt es sich um ein Platzhalterzeichen, das mit Ausnahme von `\n` mit jedem Zeichen übereinstimmt. Weitere Informationen finden Sie unter [Alle Zeichen](#AnyCharacter).  
  
- Eine allgemeine Unicode-Kategorie oder ein benannter Block. Ein Zeichen in der Eingabezeichenfolge muss einer bestimmten Unicode-Kategorie oder einem zusammenhängenden Bereich von Unicode-Zeichen angehören, damit eine Übereinstimmung vorliegt. Weitere Informationen finden Sie unter [Unicode-Kategorie oder Unicode-Block](#CategoryOrBlock).  
  
- Eine negative allgemeine Unicode-Kategorie oder ein benannter Block. Ein Zeichen in der Eingabezeichenfolge darf weder einer bestimmten Unicode-Kategorie noch einem zusammenhängenden Bereich von Unicode-Zeichen angehören, damit eine Übereinstimmung vorliegt. Weitere Informationen finden Sie unter [Negative Unicode-Kategorie oder negativer Unicode-Block](#NegativeCategoryOrBlock).  
  
- Ein Wortzeichen. Ein Zeichen in der Eingabezeichenfolge kann allen Unicode-Kategorien angehören, die für Zeichen in Wörtern geeignet sind. Weitere Informationen finden Sie unter [Wortzeichen](#WordCharacter).  
  
- Ein Nicht-Wortzeichen. Ein Zeichen in der Eingabezeichenfolge kann jeder Unicode-Kategorie angehören, bei der es sich nicht um ein Wortzeichen handelt. Weitere Informationen finden Sie unter [Nicht-Wortzeichen](#NonWordCharacter).  
  
- Ein Leerzeichen. Ein Zeichen in der Eingabezeichenfolge kann sowohl jedes Unicode-Trennzeichen als auch jedes Zeichen aus einer Anzahl von Steuerzeichen sein. Weitere Informationen finden Sie unter [Leerzeichen](#WhitespaceCharacter).  
  
- Ein Nicht-Leerzeichen. Ein Zeichen in der Eingabezeichenfolge kann jedes Nicht-Leerzeichen sein. Weitere Informationen finden Sie unter [Nicht-Leerzeichen](#NonWhitespaceCharacter).  
  
- Eine Dezimalzahl. Ein Zeichen in der Eingabezeichenfolge kann jedes als Unicode-Dezimalzeichen klassifiziertes Zeichen sein. Weitere Informationen finden Sie unter [Dezimalzeichen](#DigitCharacter).  
  
- Ein Nicht-Dezimalzeichen. Ein Zeichen in der Eingabezeichenfolge kann mit Ausnahme von Unicode-Dezimalzeichen jedes Zeichen sein. Weitere Informationen finden Sie unter [Dezimalzeichen](#NonDigitCharacter).  
  
 .NET unterstützt Zeichenklassensubtraktions-Ausdrücke. Hierdurch können Sie einen Zeichensatz definieren, der das Ergebnis des Ausschlusses einer Zeichenklasse von einer anderen darstellt. Weitere Informationen finden Sie unter [Zeichenklassensubtraktion](#CharacterClassSubtraction).  
  
> [!NOTE]
> Zeichenklassen, die Zeichen nach Kategorie abgleichen, etwa [\w](#WordCharacter) zum Abgleichen von Wortzeichen oder [\p{}](#CategoryOrBlock) zum Abgleichen mit einer Unicode-Kategorie, setzen auf der <xref:System.Globalization.CharUnicodeInfo>-Klasse auf, um Informationen zu Zeichenkategorien bereitzustellen.  Ab .NET Framework 4.6.2 basieren Zeichenkategorien auf dem [Unicode Standard, Version 8.0.0](https://www.unicode.org/versions/Unicode8.0.0/). In .NET Framework 4 bis .NET Framework 4.6.1 basieren sie auf dem [Unicode-Standard, Version 6.3.0](https://www.unicode.org/versions/Unicode6.3.0/).  
  
<a name="PositiveGroup"></a>   
## <a name="positive-character-group--"></a>Positive Zeichengruppe: [ ]  
 In einer positiven Zeichengruppe wird eine Liste von Zeichen festgelegt. Wenn eine Eingabezeichenfolge eines dieser Zeichen aufweist, liegt eine Übereinstimmung vor. Diese Zeichenliste kann einzeln, als Bereich oder beides angegeben werden.  
  
 Die Syntax zum Angeben einer Liste einzelner Zeichen lautet wie folgt:  

`[*character_group*]`

 wobei *Zeichen_Gruppe* eine Liste der einzelnen Zeichen ist, die in der Eingabezeichenfolge vorkommen können, damit eine Übereinstimmung vorliegt. *Zeichen_Gruppe* kann aus einer beliebigen Kombination von mindestens einem Literalzeichen, [Escapezeichen](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md) oder Zeichenklassen bestehen.  
  
 Die Syntax zum Angeben eines Zeichenbereichs lautet wie folgt:  
  
`[firstCharacter-lastCharacter]`  
  
 wobei *firstCharacter* das Zeichen ist, mit dem der Bereich beginnt, und *lastCharacter* das Zeichen, mit dem der Bereich endet. Ein Zeichenbereich besteht aus einer Reihe zusammenhängender Zeichen, der durch Angabe des ersten Zeichens der Reihe, eines Bindestrichs (-) und des letzten Zeichens in der Reihe definiert wird. Zwei Zeichen sind zusammenhängend, wenn sie benachbarte Unicode-Codepunkte aufweisen. *firstCharacter* muss das Zeichen mit dem niedrigeren Codepunkt sein, *lastCharacter* muss das Zeichen mit dem höheren Codepunkt sein.

> [!NOTE]
> Da eine positive Zeichengruppe sowohl einen Zeichensatz als auch einen Zeichenbereich umfassen kann, wird ein Bindestrichzeichen (`-`) immer als Bereichstrennzeichen interpretiert, sofern es nicht das erste oder das letzte Zeichen der Gruppe ist.

In der folgenden Tabelle werden einige allgemeine Muster für reguläre Ausdrücke mit positiven Zeichenklassen aufgeführt.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`[aeiou]`|Übereinstimmung mit allen Vokalen.|  
|`[\p{P}\d]`|Übereinstimmung mit allen Interpunktions- und Dezimalzeichen.|  
|`[\s\p{P}]`|Übereinstimmung mit allen Leerzeichen und Interpunktionszeichen.|  
  
 Im folgenden Beispiel wird eine positive Zeichengruppe mit den Zeichen "a" und "e" definiert. Die Eingabezeichenfolge muss daher die Wörter "grey" oder "gray" (zwei gültige Schreibweisen für die englische Form von "grau") gefolgt von einem anderen Wort aufweisen, damit eine Übereinstimmung vorliegt.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/positivecharclasses.cs#1)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/positivecharclasses.vb#1)]  
  
 Der reguläre Ausdruck `gr[ae]y\s\S+?[\s|\p{P}]` ist wie folgt definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`gr`|Übereinstimmung mit den Literalzeichen"gr".|  
|`[ae]`|Übereinstimmung mit entweder "a" oder "e".|  
|`y\s`|Übereinstimmung mit dem Literalzeichen "y" gefolgt von einem Leerzeichen.|  
|`\S+?`|Übereinstimmung mit mindestens einem, jedoch möglichst wenigen Nicht-Leerzeichen.|  
|`[\s\p{P}]`|Übereinstimmung mit entweder einem Leerzeichen oder einem Interpunktionszeichen.|  
  
 Im folgenden Beispiel liegen Übereinstimmungen mit Wörtern vor, die mit einem die oft ausgegebene Befehlszeilen  Großbuchstaben beginnen. Der Großbuchstabenbereich von A bis Z wird durch den `[A-Z]`-Unterausdruck dargestellt.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/range.cs#3)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/range.vb#3)]  
  
 Der reguläre Ausdruck `\b[A-Z]\w*\b` wird entsprechend der Darstellung in der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`[A-Z]`|Übereinstimmung mit einem die oft ausgegebene Befehlszeilen  Großbuchstaben von A bis Z.|  
|`\w*`|Übereinstimmung mit keinem oder mehreren Wortzeichen.|  
|`\b`|Übereinstimmung mit einer Wortgrenze.|  
  
<a name="NegativeGroup"></a>   
## <a name="negative-character-group-"></a>Negative Zeichengruppe: [^]  
 In einer negativen Zeichengruppe wird eine Liste von Zeichen festgelegt. Eine Eingabezeichenfolge darf keines dieser Zeichen aufweisen, damit eine Übereinstimmung vorliegt. Die Zeichenliste kann einzeln, als Bereich oder beides angegeben werden.  
  
Die Syntax zum Angeben einer Liste einzelner Zeichen lautet wie folgt:  

`[*^character_group*]`

 wobei *Zeichen_Gruppe* eine Liste der einzelnen Zeichen ist, die in der Eingabezeichenfolge nicht vorkommen können, damit eine Übereinstimmung vorliegt. *Zeichen_Gruppe* kann aus einer beliebigen Kombination von mindestens einem Literalzeichen, [Escapezeichen](../../../docs/standard/base-types/character-escapes-in-regular-expressions.md) oder Zeichenklassen bestehen.  
  
 Die Syntax zum Angeben eines Zeichenbereichs lautet wie folgt:  

`[^*firstCharacter*-*lastCharacter*]`

wobei *firstCharacter* das Zeichen ist, mit dem der Bereich beginnt, und *lastCharacter* das Zeichen, mit dem der Bereich endet. Ein Zeichenbereich besteht aus einer Reihe zusammenhängender Zeichen, der durch Angabe des ersten Zeichens der Reihe, eines Bindestrichs (-) und des letzten Zeichens in der Reihe definiert wird. Zwei Zeichen sind zusammenhängend, wenn sie benachbarte Unicode-Codepunkte aufweisen. *firstCharacter* muss das Zeichen mit dem niedrigeren Codepunkt sein, *lastCharacter* muss das Zeichen mit dem höheren Codepunkt sein.

> [!NOTE]
> Da eine negative Zeichengruppe sowohl einen Zeichensatz als auch einen Zeichenbereich umfassen kann, wird ein Bindestrichzeichen (`-`) immer als Bereichstrennzeichen interpretiert, sofern es nicht das erste oder das letzte Zeichen der Gruppe ist.
  
 Mindestens zwei Zeichenbereiche können miteinander verkettet werden. Beispiel: Verwenden Sie zum Angeben des Dezimalzeichenbereichs von "0" bis "9", des Kleinbuchstabenbereichs von "a" bis "f" und des Großbuchstabenbereichs von "A" bis "F" den Ausdruck `[0-9a-fA-F]`.  
  
 Das Zirkumflexzeichen (`^`) am Anfang einer negativen Zeichengruppe ist obligatorisch und gibt an, dass es sich um eine negative anstelle einer positiven Zeichengruppe handelt.  
  
> [!IMPORTANT]
> Bei einer negativen Zeichengruppe in einem größeren Muster eines regulären Ausdrucks handelt es sich nicht um eine Assertion mit einer Breite von Null. Dies bedeutet, dass nach dem Auswerten der negativen Zeichengruppe die Engine für reguläre Ausdrücke in der Eingabezeichenfolge zum nachfolgenden Zeichen übergeht.  
  
 In der folgenden Tabelle werden einige allgemeine Muster für reguläre Ausdrücke mit negativen Zeichengruppen aufgeführt.  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`[^aeiou]`|Übereinstimmung mit allen Zeichen mit Ausnahme von Vokalen.|  
|`[^\p{P}\d]`|Übereinstimmung mit allen Zeichen mit Ausnahme von Interpunktions- und Dezimalzeichen.|  
  
 Im folgenden Beispiel werden Übereinstimmungen für alle Wörter dargestellt, die mit den Zeichen "th" beginnen, wobei darauf kein "o" folgt.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/negativecharclasses.cs#2)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/negativecharclasses.vb#2)]  
  
 Der reguläre Ausdruck `\bth[^o]\w+\b` wird entsprechend der Darstellung in der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`th`|Übereinstimmung mit den Literalzeichen"th".|  
|`[^o]`|Übereinstimmung mit allen Zeichen außer "o".|  
|`\w+`|Übereinstimmung mit mindestens einem Wortzeichen.|  
|`\b`|An einer Wortgrenze beenden.|  
  
<a name="AnyCharacter"></a>   
## <a name="any-character-"></a>Alle Zeichen: .  
 Das Punktzeichen (.) stimmt mit Ausnahme von `\n` (dem Zeichen für einen Zeilenumbruch, "\u000A") mit allen Zeichen überein. Hierfür gelten die folgenden beiden Qualifikationen:  
  
- Wenn ein Muster für reguläre Ausdrücke durch die <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>-Option oder der Teil des Musters mit der `.`-Zeichenklasse durch die `s`-Option geändert wird, stimmt `.` mit allen Zeichen überein. Weitere Informationen finden Sie unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
     Im folgenden Beispiel wird das unterschiedliche Verhalten der `.`-Zeichenklasse in der Standardeinstellung und mit der <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>-Option veranschaulicht. Der reguläre `^.+`-Ausdruck beginnt am Anfang der Zeichenfolge und stimmt mit jedem Zeichen überein. Standardmäßig endet die Übereinstimmung am Ende der ersten Zeile. Das Muster für den regulären Ausdruck stimmt mit dem Wagenrücklaufzeichen (`\r` oder "\u000D"), jedoch nicht mit `\n` überein. Da die gesamte Eingabezeichenfolge von der <xref:System.Text.RegularExpressions.RegexOptions.Singleline?displayProperty=nameWithType>-Option als einzelne Zeile interpretiert wird, liegt für jedes enthaltene Zeichen eine Übereinstimmung vor, einschließlich `\n`.  
  
     [!code-csharp[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any2.cs#5)]
     [!code-vb[Conceptual.Regex.Language.CharacterClasses#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any2.vb#5)]  
  
> [!NOTE]
> Da für die `.`-Zeichenklasse mit Ausnahme von `\n` eine Übereinstimmung mit jedem Zeichen vorliegt, stimmt `\r` (das Wagenrücklaufzeichen, "\u000D") ebenfalls überein.  
  
- In einer positiven oder negativen Zeichengruppe wird ein Punkt anstatt einer Zeichenklasse als Literalzeichen behandelt. Weitere Informationen finden Sie weiter oben in diesem Thema unter [Positive Zeichengruppe](#PositiveGroup) und [Negative Zeichengruppe](#NegativeGroup). Im folgenden Beispiel wird zur Veranschaulichung ein regulärer Ausdruck definiert, der das Punktzeichen (`.`) sowohl als Zeichenklasse als auch als Mitglied einer positiven Zeichengruppe aufweist. Der reguläre Ausdruck `\b.*[.?!;:](\s|\z)` beginnt an einer Wortgrenze und stimmt bis zum Erreichen eines von fünf Interpunktionszeichen (einschließlich eines Punkts) mit jedem Zeichen überein. Anschließend liegt entweder eine Übereinstimmung mit einem Leerzeichen oder dem Ende der Zeichenfolge vor.  
  
     [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/any1.cs#4)]
     [!code-vb[Conceptual.RegEx.Language.CharacterClasses#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/any1.vb#4)]  
  
> [!NOTE]
> Aufgrund der Übereinstimmung des `.`-Sprachelements mit jedem Zeichen wird es häufig mit einem verzögerten Quantifizierer verwendet, wenn von einem Muster für einen regulären Ausdruck mehrere Versuche bezüglich der Übereinstimmung eines bestimmten Zeichens ausgeführt werden. Weitere Informationen finden Sie unter [Quantifizierer in regulären Ausdrücken](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
<a name="CategoryOrBlock"></a>   
## <a name="unicode-category-or-unicode-block-p"></a>Unicode-Kategorie oder Unicode-Block: \p{}  
 Jedem Zeichen wird im Unicode-Standard eine allgemeine Kategorie zugewiesen. Beispiel: Bei einem bestimmten Zeichen kann es sich um einen Großbuchstaben (dargestellt durch die `Lu`-Kategorie), ein Dezimalzeichen (die `Nd`-Kategorie), ein mathematisches Symbol (die `Sm`-Kategorie) oder einen Absatzseparator (die `Zl`-Kategorie) handeln. Bestimmte Zeichensätze im Unicode-Standard nehmen auch einen bestimmten Bereich oder einen Block aufeinander folgender Codepunkte ein. Beispielsweise befindet sich der grundlegende lateinische Zeichensatz im Bereich von "\u0000" bis "\u007F", während der arabische Zeichensatz zwischen "\u0600" und "\u06FF" liegt.  
  
 Konstrukt des regulären Ausdrucks  
  
 `\p{` *name* `}`  
  
 Übereinstimmung mit jedem Zeichen, das einer allgemeinen Unicode-Kategorie oder einem benannten Block angehört, wobei *Name* für die Abkürzung der Kategorie bzw. den Namen des benannten Blocks steht. Eine Liste von Kategorieabkürzungen finden Sie weiter unten in diesem Thema im Abschnitt [Unterstützte allgemeine Unicode-Kategorien](#SupportedUnicodeGeneralCategories). Eine Liste von benannten Blöcken finden Sie weiter unten in diesem Thema im Abschnitt [Unterstützte benannte Blöcke](#SupportedNamedBlocks).  
  
 Im folgenden Beispiel wird das `\p{`*Name*`}`-Konstrukt für eine Übereinstimmung mit sowohl einer allgemeinen Unicode-Kategorie (in diesem Fall die `Pd`-Kategorie, oder Interpunktionszeichen und Bindestriche) als auch mit einem benannten Block (`IsGreek` und `IsBasicLatin`) verwendet.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/category1.cs#6)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/category1.vb#6)]  
  
 Der reguläre Ausdruck `\b(\p{IsGreek}+(\s)?)+\p{Pd}\s(\p{IsBasicLatin}+(\s)?)+` wird entsprechend der Darstellung in der folgenden Tabelle definiert:  
  
|Muster|Beschreibung|  
|-------------|-----------------|  
|`\b`|An einer Wortgrenze beginnen.|  
|`\p{IsGreek}+`|Übereinstimmung mit mindestens einem griechischen Zeichen.|  
|`(\s)?`|Übereinstimmung mit keinem oder einem Leerzeichen.|  
|`(\p{IsGreek}+(\s)?)+`|Übereinstimmung mit dem Muster mindestens eines griechischen Zeichens, ein- oder mehrmals gefolgt von einer Null oder einem Leerzeichen.|  
|`\p{Pd}`|Übereinstimmung mit einem Interpunktionszeichen oder Bindestrich.|  
|`\s`|Entsprechung für ein Leerraumzeichen finden.|  
|`\p{IsBasicLatin}+`|Übereinstimmung mit mindestens einem grundlegenden lateinischen Zeichen.|  
|`(\s)?`|Übereinstimmung mit keinem oder einem Leerzeichen.|  
|`(\p{IsBasicLatin}+(\s)?)+`|Übereinstimmung mit dem Muster mindestens eines grundlegenden lateinischen Zeichens, ein- oder mehrmals gefolgt von einer Null oder einem Leerzeichen.|  
  
<a name="NegativeCategoryOrBlock"></a>   
## <a name="negative-unicode-category-or-unicode-block-p"></a>Negative Unicode-Kategorie oder negativer Unicode-Block: \P{}  
 Jedem Zeichen wird im Unicode-Standard eine allgemeine Kategorie zugewiesen. Beispiel: Bei einem bestimmten Zeichen kann es sich um einen Großbuchstaben (dargestellt durch die `Lu`-Kategorie), ein Dezimalzeichen (die `Nd`-Kategorie), ein mathematisches Symbol (die `Sm`-Kategorie) oder einen Absatzseparator (die `Zl`-Kategorie) handeln. Bestimmte Zeichensätze im Unicode-Standard nehmen auch einen bestimmten Bereich oder einen Block aufeinander folgender Codepunkte ein. Beispielsweise befindet sich der grundlegende lateinische Zeichensatz im Bereich von "\u0000" bis "\u007F", während der arabische Zeichensatz zwischen "\u0600" und "\u06FF" liegt.  
  
 Konstrukt des regulären Ausdrucks  
  
 `\P{` *name* `}`  
  
 Übereinstimmung mit jedem Zeichen, das weder einer allgemeinen Unicode-Kategorie noch einem benannten Block angehört, wobei *Name* für die Abkürzung der Kategorie bzw. den Namen des benannten Blocks steht. Eine Liste von Kategorieabkürzungen finden Sie weiter unten in diesem Thema im Abschnitt [Unterstützte allgemeine Unicode-Kategorien](#SupportedUnicodeGeneralCategories). Eine Liste von benannten Blöcken finden Sie weiter unten in diesem Thema im Abschnitt [Unterstützte benannte Blöcke](#SupportedNamedBlocks).  
  
 Im folgenden Beispiel wird das `\P{`*Name*`}`-Konstrukt zum Entfernen aller Währungssymbole (in diesem Fall die `Sc`-Kategorie oder Symbole und Währungen) aus numerischen Zeichenfolgen verwendet.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/notcategory1.cs#7)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/notcategory1.vb#7)]  
  
 Das Muster für den regulären `(\P{Sc})+`-Ausdruck stimmt mit mindestens einem Zeichen überein, bei dem es sich nicht um ein Währungssymbol handelt. Tatsächlich werden alle Währungssymbole aus der Ergebniszeichenfolge entfernt.  
  
<a name="WordCharacter"></a>   
## <a name="word-character-w"></a>Wortzeichen: \w  
 `\w` entspricht einem beliebigen Wortzeichen. Ein Wortzeichen gehört einer der in der folgenden Tabelle aufgeführten Unicode-Kategorien an.  
  
|Kategorie|Beschreibung|  
|--------------|-----------------|  
|Ll|Letter, Lowercase (Buchstabe, Kleinschreibung)|  
|Lu|Letter, Uppercase (Buchstabe, Großschreibung)|  
|Lt|Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)|  
|Lo|Letter, Other (Buchstabe, andere)|  
|Lm|Letter, Modifier (Buchstabe, Modifizierer)|  
|Mn|Mark, Nonspacing (Satzzeichen, ohne horizontalen Vorschub)|  
|Nd|Number, Decimal Digit (Zahl, Dezimalzahl)|  
|Pc|Punctuation, Connector (Interpunktion, Konnektor). Zu dieser Kategorie gehören zehn Zeichen, von denen das UNTERSTRICH-Zeichen "u+005F" (_) am häufigsten verwendet wird.|  
  
 Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht `\w` dem `[a-zA-Z_0-9]`-Ausdruck. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt „ECMAScript-Vergleichsverhalten“ unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
> [!NOTE]
> Aufgrund der Übereinstimmung des `\w`-Sprachelements mit jedem Wortzeichen wird es häufig mit einem verzögerten Quantifizierer verwendet, wenn ein Muster für einen regulären Ausdruck mehrmals versucht, eine Übereinstimmung mit einem beliebigen Wortzeichen, gefolgt von einem bestimmten Wortzeichen, herzustellen. Weitere Informationen finden Sie unter [Quantifizierer in regulären Ausdrücken](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
 Im folgenden Beispiel werden mit dem `\w`-Sprachelement übereinstimmende doppelte Zeichen innerhalb eines Worts ermittelt. Im Beispiel wird ein Muster für reguläre Ausdrücke definiert (`(\w)\1`), das wie folgt interpretiert werden kann.  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|(\w)|Übereinstimmung mit einem Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|\1|Übereinstimmung mit dem Wert der ersten Erfassung.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/wordchar1.cs#8)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/wordchar1.vb#8)]  
  
<a name="NonWordCharacter"></a>   
## <a name="non-word-character-w"></a>Nicht-Wortzeichen: \W  
 `\W` entspricht einem beliebigen Nichtwortzeichen. Das \W-Sprachelement entspricht der folgenden Zeichenklasse:  
  
`[^\p{Ll}\p{Lu}\p{Lt}\p{Lo}\p{Nd}\p{Pc}\p{Lm}]`  
  
 Anders ausgedrückt: Mit Ausnahme der Zeichen, die in den Unicode-Kategorien enthalten sind, die in der folgenden Tabelle aufgelistet werden, liegt eine Übereinstimmung mit jedem Zeichen vor.  
  
|Kategorie|Beschreibung|  
|--------------|-----------------|  
|Ll|Letter, Lowercase (Buchstabe, Kleinschreibung)|  
|Lu|Letter, Uppercase (Buchstabe, Großschreibung)|  
|Lt|Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)|  
|Lo|Letter, Other (Buchstabe, andere)|  
|Lm|Letter, Modifier (Buchstabe, Modifizierer)|  
|Mn|Mark, Nonspacing (Satzzeichen, ohne horizontalen Vorschub)|  
|Nd|Number, Decimal Digit (Zahl, Dezimalzahl)|  
|Pc|Punctuation, Connector (Interpunktion, Konnektor). Zu dieser Kategorie gehören zehn Zeichen, von denen das UNTERSTRICH-Zeichen "u+005F" (_) am häufigsten verwendet wird.|  
  
 Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht `\W` dem `[^a-zA-Z_0-9]`-Ausdruck. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt „ECMAScript-Vergleichsverhalten“ unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
> [!NOTE]
> Aufgrund der Übereinstimmung des `\W`-Sprachelements mit jedem Nichtwortzeichen wird es häufig mit einem verzögerten Quantifizierer verwendet, wenn ein Muster für einen regulären Ausdruck mehrmals versucht, eine Übereinstimmung mit einem beliebigen Nichtwortzeichen, gefolgt von einem bestimmten Nichtwortzeichen, herzustellen. Weitere Informationen finden Sie unter [Quantifizierer in regulären Ausdrücken](../../../docs/standard/base-types/quantifiers-in-regular-expressions.md).  
  
 Das folgende Beispiel veranschaulicht die `\W`-Zeichenklasse.  Hierfür wird ein Muster für einen regulären Ausdruck definiert (`\b(\w+)(\W){1,2}`), das mit einem von einem oder zwei Nichtwortzeichen (z. B. Leer- oder Interpunktionszeichen) gefolgten Wort übereinstimmt. Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|\b|Der Vergleich beginnt an einer Wortgrenze.|  
|(\w+)|Übereinstimmung mit mindestens einem Wortzeichen. Dies ist die erste Erfassungsgruppe.|  
|(\W){1,2}|Übereinstimmung mit einem Nicht-Wortzeichen (ein- oder zweimal). Dies ist die zweite Erfassungsgruppe.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwordchar1.cs#9)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwordchar1.vb#9)]  
  
 Da das <xref:System.Text.RegularExpressions.Group>-Objekt für die zweite Erfassungsgruppe nur ein einzelnes erfasstes Nicht-Wortzeichen aufweist, werden im Beispiel alle erfassten Nicht-Wortzeichen aus dem von der <xref:System.Text.RegularExpressions.CaptureCollection>-Eigenschaft zurückgegebenen <xref:System.Text.RegularExpressions.Group.Captures%2A?displayProperty=nameWithType>-Objekt abgerufen.  
  
<a name="WhitespaceCharacter"></a>   
## <a name="whitespace-character-s"></a>Leerraumzeichen: \s  
 `\s` entspricht einem beliebigen Zeichen für Leerraum. Dies ist zu den in der folgenden Tabelle aufgeführten Escapesequenzen und Unicode-Kategorien äquivalent.  
  
|Kategorie|Beschreibung|  
|--------------|-----------------|  
|`\f`|Seitenvorschubzeichen, "\u000C".|  
|`\n`|Zeilenumbruchzeichen, "\u000A".|  
|`\r`|Wagenrücklaufzeichen, "\u000D".|  
|`\t`|Tabstoppzeichen, "\u0009".|  
|`\v`|Vertikales Tabstoppzeichen, "\u000B".|  
|`\x85`|Auslassungs- oder NÄCHSTE ZEILE (NEL)-Zeichen (…), "\u0085".|  
|`\p{Z}`|Übereinstimmung mit jedem Trennzeichen.|  
  
 Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht `\s` dem `[ \f\n\r\t\v]`-Ausdruck. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt „ECMAScript-Vergleichsverhalten“ unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
 Das folgende Beispiel veranschaulicht die `\s`-Zeichenklasse. Hierfür wird ein Muster für einen regulären Ausdruck definiert (`\b\w+(e)?s(\s|$)`), das mit einem entweder auf "s" oder "es" endenden Wort übereinstimmt. Auf dieses Wort muss ein Leerzeichen oder das Ende der Eingabezeichenfolge folgen. Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|\b|Der Vergleich beginnt an einer Wortgrenze.|  
|\w+|Übereinstimmung mit mindestens einem Wortzeichen.|  
|(e)?|Übereinstimmung mit "e", entweder null- oder einmal.|  
|s|Übereinstimmung mit "s".|  
|(\s&#124;$)|Übereinstimmung mit entweder einem Leerzeichen oder dem Ende der Eingabezeichenfolge.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/whitespace1.cs#10)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/whitespace1.vb#10)]  
  
<a name="NonWhitespaceCharacter"></a>   
## <a name="non-whitespace-character-s"></a>Nicht-Leerraumzeichen: \S  
 `\S` entspricht einem beliebigen Nichtleerraumzeichen. Dies ist äquivalent zum Muster für den regulären `[^\f\n\r\t\v\x85\p{Z}]`-Ausdruck bzw. das Gegenteil des Musters für den regulären Ausdruck, der `\s` entspricht und daher mit Leerzeichen übereinstimmt. Weitere Informationen finden Sie unter [Leerzeichen: \s](#WhitespaceCharacter).  
  
 Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht `\S` dem `[^ \f\n\r\t\v]`-Ausdruck. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt „ECMAScript-Vergleichsverhalten“ unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
 Im folgenden Beispiel wird das `\S`-Sprachelement veranschaulicht. Das Muster für den regulären Ausdruck `\b(\S+)\s?` stimmt mit durch Leerzeichen getrennten Zeichenfolgen überein. Das zweite Element im <xref:System.Text.RegularExpressions.GroupCollection>-Objekt der Übereinstimmung enthält die entsprechende Zeichenfolge. Der reguläre Ausdruck kann wie in der folgenden Tabelle dargestellt interpretiert werden.  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`\b`|Der Vergleich beginnt an einer Wortgrenze.|  
|`(\S+)`|Übereinstimmung mit mindestens einem Nicht-Leerzeichen. Dies ist die erste Erfassungsgruppe.|  
|`\s?`|Übereinstimmung mit keinem oder einem Leerzeichen.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nonwhitespace1.cs#11)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nonwhitespace1.vb#11)]  
  
<a name="DigitCharacter"></a>   
## <a name="decimal-digit-character-d"></a>Dezimalzahl: \d  
 `\d` entspricht einer beliebigen Dezimalziffer. Dies entspricht dem Muster des regulären `\p{Nd}`-Ausdrucks, das neben den Standarddezimalzahlen 0 bis 9 auch die Dezimalzahlen einer Anzahl anderer Zeichensätze einschließt.  
  
 Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht `\d` dem `[0-9]`-Ausdruck. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt „ECMAScript-Vergleichsverhalten“ unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
 Im folgenden Beispiel wird das `\d`-Sprachelement veranschaulicht. Anhand eines Tests soll ermittelt werden, ob eine Eingabezeichenfolge eine gültige Telefonnummer in den USA und Kanada darstellt. Das Muster für reguläre Ausdrücke `^(\(?\d{3}\)?[\s-])?\d{3}-\d{4}$` wird entsprechend der folgenden Tabelle definiert:  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`^`|Beginnt den Vergleich am Anfang der Eingabezeichenfolge.|  
|`\(?`|Übereinstimmung mit null oder einem Literalzeichen ("(").|  
|`\d{3}`|Entsprechung für drei Dezimalstellen finden.|  
|`\)?`|Übereinstimmung mit null oder einem Literalzeichen (")").|  
|`[\s-]`|Übereinstimmung mit einem Bindestrich oder Leerzeichen.|  
|`(\(?\d{3}\)?[\s-])?`|Übereinstimmung mit einer optionalen öffnenden Klammer gefolgt von drei Dezimalzahlen, einer optionalen schließenden Klammer sowie entweder null- oder einmal von einem Leerzeichen oder Bindestrich. Dies ist die erste Erfassungsgruppe.|  
|`\d{3}-\d{4}`|Übereinstimmung mit drei Dezimalzahlen gefolgt von einem Bindestrich und vier zusätzlichen Dezimalzahlen.|  
|`$`|Entsprechung für das Ende der Eingabezeichenfolge finden.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/digit1.cs#12)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/digit1.vb#12)]  
  
<a name="NonDigitCharacter"></a>   
## <a name="non-digit-character-d"></a>Nicht-Zahlen: \D  
 `\D` stimmt mit jedem Zeichen außer Zahlen überein. Dies entspricht dem Muster des regulären Ausdrucks `\P{Nd}`.  
  
 Bei Angabe von ECMAScript-kompatiblem Verhalten entspricht `\D` dem `[^0-9]`-Ausdruck. Weitere Informationen zu regulären ECMAScript-Ausdrücken finden Sie im Abschnitt „ECMAScript-Vergleichsverhalten“ unter [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md).  
  
 Im folgenden Beispiel wird das "\D"-Sprachelement veranschaulicht. Anhand eines Tests wird ermittelt, ob eine Zeichenfolge (z. B. eine Teilenummer) aus der gewünschten Kombination von Dezimalzahlen und Nicht-Dezimalzahlen besteht. Das Muster für reguläre Ausdrücke `^\D\d{1,5}\D*$` wird entsprechend der folgenden Tabelle definiert:  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|`^`|Beginnt den Vergleich am Anfang der Eingabezeichenfolge.|  
|`\D`|Übereinstimmung mit jedem Zeichen außer Zahlen.|  
|`\d{1,5}`|Übereinstimmung mit einer bis fünf Dezimalzahlen.|  
|`\D*`|Übereinstimmung mit null, einem oder mehreren Nichtdezimalzeichen.|  
|`$`|Entsprechung für das Ende der Eingabezeichenfolge finden.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/nondigit1.cs#13)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#13](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/nondigit1.vb#13)]  
  
<a name="SupportedUnicodeGeneralCategories"></a>   
## <a name="supported-unicode-general-categories"></a>Unterstützte allgemeine Unicode-Kategorien  
 In der folgenden Tabelle werden die allgemeinen, in Unicode definierten Kategorien aufgeführt. Weitere Informationen finden Sie in den Unterthemen „UCD File Format“ (UCD-Dateiformat) und „General Category Values“ (Allgemeine Kategorienwerte) der [Unicode Character Database](https://www.unicode.org/reports/tr44/).  
  
|Kategorie|Beschreibung|  
|--------------|-----------------|  
|`Lu`|Letter, Uppercase (Buchstabe, Großschreibung)|  
|`Ll`|Letter, Lowercase (Buchstabe, Kleinschreibung)|  
|`Lt`|Letter, Titlecase (Buchstabe, großer Anfangsbuchstabe)|  
|`Lm`|Letter, Modifier (Buchstabe, Modifizierer)|  
|`Lo`|Letter, Other (Buchstabe, andere)|  
|`L`|Alle Buchstaben. Hierzu zählen die Zeichen `Lu`, `Ll`, `Lt`, `Lm` und `Lo`.|  
|`Mn`|Mark, Nonspacing (Satzzeichen, ohne horizontalen Vorschub)|  
|`Mc`|Mark, Spacing Combining (Satzzeichen, Kombinationszeichen mit Vorschub)|  
|`Me`|Mark, Enclosing (Satzzeichen, einschließend)|  
|`M`|Alle diakritischen Zeichen. Hierzu zählen die Kategorien `Mn`, `Mc` und `Me`.|  
|`Nd`|Number, Decimal Digit (Zahl, Dezimalzahl)|  
|`Nl`|Number, Letter (Zahl, Buchstabe)|  
|`No`|Number, Other (Zahl, andere)|  
|`N`|Alle Zahlen. Hierzu zählen die Kategorien `Nd`, `Nl` und `No`.|  
|`Pc`|Punctuation, Connector (Interpunktion, Konnektor)|  
|`Pd`|Punctuation, Dash (Interpunktion, Bindestrich)|  
|`Ps`|Punctuation, Open (Interpunktion, öffnend)|  
|`Pe`|Punctuation, Close (Interpunktion, schließend)|  
|`Pi`|Punctuation, Initial quote (Interpunktion, öffnendes Anführungszeichen; kann sich je nach Verwendung wie "Ps" oder "Pe" verhalten)|  
|`Pf`|Punctuation, Final quote (Interpunktion, schließendes Anführungszeichen; kann sich je nach Verwendung wie "Ps" oder "Pe" verhalten)|  
|`Po`|Punctuation, Other (Interpunktion, andere)|  
|`P`|Alle Interpunktionszeichen. Hierzu zählen die Kategorien `Pc`, `Pd`, `Ps`, `Pe`, `Pi`, `Pf` und `Po`.|  
|`Sm`|Symbol, Math (Symbol, Mathematik)|  
|`Sc`|Symbol, Currency (Symbol, Währung)|  
|`Sk`|Symbol, Modifier (Symbol, Modifizierer)|  
|`So`|Symbol, Other (Symbol, andere)|  
|`S`|Alle Symbole. Hierzu zählen die Kategorien `Sm`, `Sc`, `Sk` und `So`.|  
|`Zs`|Separator, Space (Trennzeichen, Leerzeichen)|  
|`Zl`|Separator, Line (Trennzeichen, Zeile)|  
|`Zp`|Separator, Paragraph (Trennzeichen, Absatz)|  
|`Z`|Alle Trennzeichen. Hierzu zählen die Kategorien `Zs`, `Zl` und `Zp`.|  
|`Cc`|Other, Control (Andere, Steuerzeichen)|  
|`Cf`|Other, Format (Andere, Format)|  
|`Cs`|Other, Surrogate (Andere, Ersatzzeichen)|  
|`Co`|Other, Private Use (Andere, persönliche Verwendung)|  
|`Cn`|Other, Not Assigned (Andere, nicht zugewiesen; kein Zeichen weist diese Eigenschaft auf)|  
|`C`|Alle Steuerzeichen. Hierzu zählen die Kategorien `Cc`, `Cf`, `Cs`, `Co` und `Cn`.|  
  
 Sie können die Unicode-Kategorie eines bestimmten Zeichens ermitteln, indem Sie das Zeichen an die <xref:System.Char.GetUnicodeCategory%2A>-Methode übergeben. Im folgenden Beispiel wird mithilfe der <xref:System.Char.GetUnicodeCategory%2A>-Methode die Kategorie jedes Elements in einem Array mit ausgewählten lateinischen Zeichen ermittelt.  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/getunicodecategory1.cs#14)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/getunicodecategory1.vb#14)]  
  
<a name="SupportedNamedBlocks"></a>   
## <a name="supported-named-blocks"></a>Unterstützte benannte Blöcke

In der folgenden Tabelle werden die von .NET bereitgestellten benannten Blöcke aufgelistet. Der Satz von unterstützten benannten Blöcke basiert auf Unicode 4.0 und Perl 5.6. Einen regulären Ausdruck, der benannte Blöcke verwendet, finden Sie im Abschnitt [Unicode-Kategorie oder Unicode-Block: \\p{}](#unicode-category-or-unicode-block-p).  
  
|Codepunktbereich|Blockname|  
|----------------------|----------------|  
|0000 - 007F|`IsBasicLatin`|  
|0080 - 00FF|`IsLatin-1Supplement`|  
|0100 - 017F|`IsLatinExtended-A`|  
|0180 - 024F|`IsLatinExtended-B`|  
|0250 - 02AF|`IsIPAExtensions`|  
|02B0 - 02FF|`IsSpacingModifierLetters`|  
|0300 - 036F|`IsCombiningDiacriticalMarks`|  
|0370 - 03FF|`IsGreek`<br /><br /> - oder -<br /><br /> `IsGreekandCoptic`|  
|0400 - 04FF|`IsCyrillic`|  
|0500 - 052F|`IsCyrillicSupplement`|  
|0530 - 058F|`IsArmenian`|  
|0590 - 05FF|`IsHebrew`|  
|0600 - 06FF|`IsArabic`|  
|0700 - 074F|`IsSyriac`|  
|0780 - 07BF|`IsThaana`|  
|0900 - 097F|`IsDevanagari`|  
|0980 - 09FF|`IsBengali`|  
|0A00 - 0A7F|`IsGurmukhi`|  
|0A80 - 0AFF|`IsGujarati`|  
|0B00 - 0B7F|`IsOriya`|  
|0B80 - 0BFF|`IsTamil`|  
|0C00 - 0C7F|`IsTelugu`|  
|0C80 - 0CFF|`IsKannada`|  
|0D00 - 0D7F|`IsMalayalam`|  
|0D80 - 0DFF|`IsSinhala`|  
|0E00 - 0E7F|`IsThai`|  
|0E80 - 0EFF|`IsLao`|  
|0F00 - 0FFF|`IsTibetan`|  
|1000 - 109F|`IsMyanmar`|  
|10A0 - 10FF|`IsGeorgian`|  
|1100 - 11FF|`IsHangulJamo`|  
|1200 - 137F|`IsEthiopic`|  
|13A0 - 13FF|`IsCherokee`|  
|1400 - 167F|`IsUnifiedCanadianAboriginalSyllabics`|  
|1680 - 169F|`IsOgham`|  
|16A0 - 16FF|`IsRunic`|  
|1700 - 171F|`IsTagalog`|  
|1720 - 173F|`IsHanunoo`|  
|1740 - 175F|`IsBuhid`|  
|1760 - 177F|`IsTagbanwa`|  
|1780 - 17FF|`IsKhmer`|  
|1800 - 18AF|`IsMongolian`|  
|1900 - 194F|`IsLimbu`|  
|1950 - 197F|`IsTaiLe`|  
|19E0 - 19FF|`IsKhmerSymbols`|  
|1D00 - 1D7F|`IsPhoneticExtensions`|  
|1E00 - 1EFF|`IsLatinExtendedAdditional`|  
|1F00 - 1FFF|`IsGreekExtended`|  
|2000 - 206F|`IsGeneralPunctuation`|  
|2070 - 209F|`IsSuperscriptsandSubscripts`|  
|20A0 - 20CF|`IsCurrencySymbols`|  
|20D0 - 20FF|`IsCombiningDiacriticalMarksforSymbols`<br /><br /> - oder -<br /><br /> `IsCombiningMarksforSymbols`|  
|2100 - 214F|`IsLetterlikeSymbols`|  
|2150 - 218F|`IsNumberForms`|  
|2190 - 21FF|`IsArrows`|  
|2200 - 22FF|`IsMathematicalOperators`|  
|2300 - 23FF|`IsMiscellaneousTechnical`|  
|2400 - 243F|`IsControlPictures`|  
|2440 - 245F|`IsOpticalCharacterRecognition`|  
|2460 - 24FF|`IsEnclosedAlphanumerics`|  
|2500 - 257F|`IsBoxDrawing`|  
|2580 - 259F|`IsBlockElements`|  
|25A0 - 25FF|`IsGeometricShapes`|  
|2600 - 26FF|`IsMiscellaneousSymbols`|  
|2700 - 27BF|`IsDingbats`|  
|27C0 - 27EF|`IsMiscellaneousMathematicalSymbols-A`|  
|27F0 - 27FF|`IsSupplementalArrows-A`|  
|2800 - 28FF|`IsBraillePatterns`|  
|2900 - 297F|`IsSupplementalArrows-B`|  
|2980 - 29FF|`IsMiscellaneousMathematicalSymbols-B`|  
|2A00 - 2AFF|`IsSupplementalMathematicalOperators`|  
|2B00 - 2BFF|`IsMiscellaneousSymbolsandArrows`|  
|2E80 - 2EFF|`IsCJKRadicalsSupplement`|  
|2F00 - 2FDF|`IsKangxiRadicals`|  
|2FF0 - 2FFF|`IsIdeographicDescriptionCharacters`|  
|3000 - 303F|`IsCJKSymbolsandPunctuation`|  
|3040 - 309F|`IsHiragana`|  
|30A0 - 30FF|`IsKatakana`|  
|3100 - 312F|`IsBopomofo`|  
|3130 - 318F|`IsHangulCompatibilityJamo`|  
|3190 - 319F|`IsKanbun`|  
|31A0 - 31BF|`IsBopomofoExtended`|  
|31F0 - 31FF|`IsKatakanaPhoneticExtensions`|  
|3200 - 32FF|`IsEnclosedCJKLettersandMonths`|  
|3300 - 33FF|`IsCJKCompatibility`|  
|3400 - 4DBF|`IsCJKUnifiedIdeographsExtensionA`|  
|4DC0 - 4DFF|`IsYijingHexagramSymbols`|  
|4E00 - 9FFF|`IsCJKUnifiedIdeographs`|  
|A000 - A48F|`IsYiSyllables`|  
|A490 - A4CF|`IsYiRadicals`|  
|AC00 - D7AF|`IsHangulSyllables`|  
|D800 - DB7F|`IsHighSurrogates`|  
|DB80 - DBFF|`IsHighPrivateUseSurrogates`|  
|DC00 - DFFF|`IsLowSurrogates`|  
|E000 - F8FF|`IsPrivateUse` oder `IsPrivateUseArea`|  
|F900 - FAFF|`IsCJKCompatibilityIdeographs`|  
|FB00 - FB4F|`IsAlphabeticPresentationForms`|  
|FB50 - FDFF|`IsArabicPresentationForms-A`|  
|FE00 - FE0F|`IsVariationSelectors`|  
|FE20 - FE2F|`IsCombiningHalfMarks`|  
|FE30 - FE4F|`IsCJKCompatibilityForms`|  
|FE50 - FE6F|`IsSmallFormVariants`|  
|FE70 - FEFF|`IsArabicPresentationForms-B`|  
|FF00 - FFEF|`IsHalfwidthandFullwidthForms`|  
|FFF0 - FFFF|`IsSpecials`|  
  
<a name="CharacterClassSubtraction"></a>   
## <a name="character-class-subtraction-base_group---excluded_group"></a>Zeichenklassensubtraktion: [base_group - [excluded_group]]  
 Eine Zeichenklasse definiert einen Satz von Zeichen. Durch Zeichenklassensubtraktion erhalten Sie einen Zeichensatz, der das Ergebnis des Ausschlusses der Zeichen einer Zeichenklasse von einer anderen darstellt.  
  
 Ein Zeichenklassensubtraktionsausdruck weist folgende Form auf:  
  
 `[` *base_group* `-[` *excluded_group* `]]`  
  
 Die eckigen Klammern (`[]`) und der Bindestrich (`-`) sind obligatorisch. Bei der *Basisgruppe* handelt es sich um eine [positive Zeichengruppe](#PositiveGroup) oder eine [negative Zeichengruppe](#NegativeGroup). Die Komponente *ausgeschlossene_Gruppe* stellt eine andere positive oder negative Zeichengruppe bzw. einen anderen Zeichenklassensubtraktions-Ausdruck dar (d.h. Sie können Zeichenklassensubtraktions-Ausdrücke schachteln).  
  
 Beispiel: Angenommen, Sie verfügen über eine Basisgruppe, die aus dem Zeichenbereich von "a" bis "z" besteht. Zum Definieren eines Zeichensatzes, der mit Ausnahme des Zeichens "m" aus der Basisgruppe besteht, verwenden Sie `[a-z-[m]]`. Zum Definieren eines Zeichensatzes, der mit Ausnahme der Zeichen "d", "j" und "p" aus der Basisgruppe besteht, verwenden Sie `[a-z-[djp]]`. Zum Definieren eines Zeichensatzes, der mit Ausnahme des Zeichenbereichs von "m" bis "p" aus der Basisgruppe besteht, verwenden Sie `[a-z-[m-p]]`.  
  
 Betrachten Sie den geschachtelten `[a-z-[d-w-[m-o]]]`-Zeichenklassensubtraktionsausdruck. Der Ausdruck wird vom innersten Zeichenbereich nach außen ausgewertet. Zuerst wird der Zeichenbereich von "m" bis "o" vom Zeichenbereich "d" bis "w" subtrahiert. Das Ergebnis stellt einen Satz von Zeichen von "d" bis "l" und von "p" bis "w" dar. Dieser Satz wird anschließend vom Zeichenbereich "a" bis "z" subtrahiert, sodass sich der Zeichensatz `[abcmnoxyz]` ergibt.  
  
 Für die Zeichenklassensubtraktion kann jede Zeichenklasse verwendet werden. Zum Definieren eines Zeichensatzes, der aus allen Unicode-Zeichen von "\u0000" bis "\uFFFF" mit Ausnahme von Leerzeichen (`\s`), der Zeichen in der allgemeinen Interpunktionskategorie (`\p{P}`), der Zeichen im benannten Block `IsGreek` (`\p{IsGreek}`) und des Unicode-Steuerzeichens NEXT LINE (\x85) besteht, verwenden Sie `[\u0000-\uFFFF-[\s\p{P}\p{IsGreek}\x85]]`.  
  
 Wählen Sie für einen Zeichenklassensubtraktionsausdruck Zeichenklassen aus, mit denen nützliche Ergebnisse erzielt werden können. Vermeiden Sie Ausdrücke, die einen leeren Satz von Zeichen ergeben, mit nichts übereinstimmen oder ein Äquivalent der ursprünglichen Basisgruppe darstellen. Beispielsweise ergibt der Ausdruck `[\p{IsBasicLatin}-[\x00-\x7F]]`, durch den alle Zeichen des Zeichenbereichs `IsBasicLatin` von der allgemeinen Kategorie `IsBasicLatin` subtrahiert werden, einen leeren Zeichensatz. Gleichermaßen ist die ursprüngliche Basisgruppe das Ergebnis des Ausdrucks `[a-z-[0-9]]`.  Der Grund hierfür ist, dass die Basisgruppe (der Zeichenbereich der Buchstaben von "a" bis "z") keine Zeichen aus der ausgeschlossenen Gruppe (dem Zeichenbereich der Dezimalzahlen von "0" bis "9") aufweist.  
  
 Im folgenden Beispiel wird ein regulärer Ausdruck definiert (`^[0-9-[2468]]+$`), der in einer Eingabezeichenfolge Übereinstimmungen für Null und ungerade Zahlen ergibt.  Der reguläre Ausdruck wird entsprechend der Darstellung in der folgenden Tabelle interpretiert.  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|^|Beginnt am Anfang der Eingabezeichenfolge mit der Übereinstimmung.|  
|`[0-9-[2468]]+`|Mindestens eine Übereinstimmung mit einem Zeichen von 0 bis 9 (mit Ausnahme von 2, 4, 6 und 8) liegt vor. Anders ausgedrückt: Es liegt mindestens eine Übereinstimmung mit Null oder einer ungeraden Zahl vor.|  
|$|Ende des Abgleichs am Ende der Eingabezeichenfolge.|  
  
 [!code-csharp[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.regex.language.characterclasses/cs/classsubtraction1.cs#15)]
 [!code-vb[Conceptual.RegEx.Language.CharacterClasses#15](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.regex.language.characterclasses/vb/classsubtraction1.vb#15)]  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Char.GetUnicodeCategory%2A>
- [Sprachelemente für reguläre Ausdrücke – Kurzübersicht](../../../docs/standard/base-types/regular-expression-language-quick-reference.md)
- [Optionen für reguläre Ausdrücke](../../../docs/standard/base-types/regular-expression-options.md)
