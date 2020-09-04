---
title: Symbol- und Operatorenreferenz
description: Hier erfahren Sie mehr über die Symbole und Operatoren, die in der F#-Programmiersprache verwendet werden.
ms.date: 08/15/2020
fl_keywords:
- '|>_FS'
ms.openlocfilehash: 5943352f0a1710ba7a666a79b7871b7269c75a6b
ms.sourcegitcommit: ae2e8a61a93c5cf3f0035c59e6b064fa2f812d14
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "89359089"
---
# <a name="symbol-and-operator-reference"></a>Symbol- und Operatorenreferenz

Dieser Artikel enthält eine Tabelle mit Symbolen und Operatoren, die in der Sprache F# verwendet werden.

## <a name="table-of-symbols-and-operators"></a>Tabelle der Symbole und Operatoren

In der folgenden Tabelle werden die in der Sprache F# verwendeten Symbole beschrieben, zudem sind eine kurze Beschreibung zu den Verwendungszwecken und weiterführende Links enthalten. Symbole sind nach dem ASCII-Zeichensatz sortiert.

|Symbol oder Operator|Links|BESCHREIBUNG|
|------------------|-----|-----------|
|`!`|[Referenzzellen](../reference-cells.md)<br /><br />[Berechnungsausdrücke](../computation-expressions.md)|<ul><li>Dereferenziert eine Verweiszelle.<br /></li><li>Nach einem Schlüsselwort weist dies auf eine geänderte Version des von einem Workflow gesteuerten Verhaltens des Schlüsselworts hin.<br /></li></ul>|
|`!=`||<ul><li>Nicht in F# verwendet. Verwenden Sie `<>` für Ungleichheitsoperationen.<br /></li></ul>|
|`"`|[Literale](../literals.md)<br /><br />[Zeichenfolgen](../strings.md)|<ul><li>Begrenzt eine Textzeichenfolge.<br /></li></ul>|
|`"""`|[Zeichenfolgen](../strings.md)|Begrenzt eine wörtliche Textzeichenfolge. Unterscheidet sich insofern von `@"..."`, dass Sie mit einem einfachen Anführungszeichen in der Zeichenfolge ein Anführungszeichen angeben können.|
|`#`|[Compileranweisungen](../compiler-directives.md)<br /><br />[Flexible Typen](../flexible-types.md)|<ul><li>Präfix für eine Präprozessor- oder Compilerdirektive, z. B. `#light`.<br /></li><li>Gibt bei Verwendung mit einem Typ einen *flexiblen Typ* an, der auf einen Typ oder einen seiner abgeleiteten Typen verweist.<br /></li></ul>|
|`$`||<ul><li>Wird intern für bestimmte vom Compiler generierte Variablen- und Funktionsnamen verwendet.<br /></li></ul>|
|`%`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)<br /><br />[Zitieren von Code](../code-quotations.md)|<ul><li>Berechnet den ganzzahligen Rest<br /></li><li>Wird beim Splicing von Ausdrücken in typisierte Codequotationen verwendet.<br /></li></ul>|
|`%%`|[Zitieren von Code](../code-quotations.md)|<ul><li>Wird beim Splicing von Ausdrücken in nicht typisierte Codequotationen verwendet.<br /></li></ul>|
|`%?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Berechnet den ganzzahligen Rest, wenn die rechte Seite ein Nullable-Typ ist<br /></li></ul>|
|`&`|[Vergleichsausdrücke](../match-expressions.md)|<ul><li>Berechnet die Adresse eines änderbaren Werts, der bei der Interoperation mit anderen Sprachen verwendet werden kann.<br /></li><li>Wird in AND-Mustern verwendet.<br /></li></ul>|
|`&&`|[Boolesche Operatoren](boolean-operators.md)|<ul><li>Berechnet die boolesche AND-Operation.<br /></li></ul>|
|`&&&`|[Bitwise Operators (Bitweise Operatoren)](bitwise-operators.md)|<ul><li>Berechnet die bitweise AND-Operation.<br /></li></ul>|
|`'`|[Literale](../literals.md)<br /><br />[Automatische Verallgemeinerung](../generics/automatic-generalization.md)|<ul><li>Begrenzt ein Literal mit einem Zeichen.<br /></li><li>Gibt einen generischen Typparameter an.<br /></li></ul>|
|<code>&#96;&#96;...&#96;&#96;</code>||<ul><li>Begrenzt einen Bezeichner, der ansonsten kein gültiger Bezeichner wäre, z. B. ein Sprachschlüsselwort.<br /></li></ul>|
|`( )`|[Unit-Typ](../unit-type.md)|<ul><li>Stellt den einzelnen Wert des Einheitentyps dar.<br /></li></ul>|
|`(...)`|[Tupel](../tuples.md)<br /><br />[Operatorüberladung](../operator-overloading.md)|<ul><li>Gibt die Reihenfolge an, in der Ausdrücke ausgewertet werden.<br /></li><li>Begrenzt ein Tupel.<br /></li><li>Wird in Operatordefinitionen verwendet.<br /></li></ul>|
|`(*...*)`||<ul><li>Begrenzt einen Kommentar, der mehrere Zeilen umfassen kann.<br /></li></ul>|
|<code>(&#124;...&#124;)</code>|[Aktive Muster](../active-patterns.md)|<ul><li>Begrenzt ein aktives Muster. Wird auch als *Bananenklammern* bezeichnet.<br /></li></ul>|
|`*`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)<br /><br />[Tupel](../tuples.md)<br /><br />[Maßeinheiten](../units-of-measure.md)|<ul><li>Bei Verwendung als binärer Operator wird die linke mit der rechten Seite multipliziert.<br /></li><li>Gibt in Typen die Paarung in einem Tupel an.<br /></li><li>Wird in Maßeinheittypen verwendet.<br /></li></ul>|
|`*?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Multipliziert die linke mit der rechten Seite, wenn die rechte Seite ein Typ ist, der Null-Werte zulässt.<br /></li></ul>|
|`**`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)|<ul><li>Berechnet die Potenzierung (`x ** y` steht für `x` potenziert mit `y`).<br /></li></ul>|
|`+`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)|<ul><li>Bei Verwendung als binärer Operator werden die linke und die rechte Seite addiert.<br /></li><li>Gibt bei Verwendung als unärer Operator eine positive Menge an. (Formell erzeugt es den gleichen Wert bei unverändertem Vorzeichen.)<br /></li></ul>|
|`+?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Addiert die linke und die rechte Seite, wenn die rechte Seite ein Typ ist, der Null-Werte zulässt.<br /></li></ul>|
|`,`|[Tupel](../tuples.md)|<ul><li>Trennt die Elemente eines Tupels oder Typparameters.<br /></li></ul>|
|`-`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)|<ul><li>Bei Verwendung als binärer Operator wird rechte Seite von der linken subtrahiert.<br /></li><li>Führt bei Verwendung als unärer Operator eine Negationsoperation aus.<br /></li></ul>|
|`-?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Subtrahiert die rechte Seite von der linken, wenn die rechte Seite ein Typ ist, der Null-Werte zulässt.<br /></li></ul>|
|`->`|[Funktionen](../functions/index.md)<br /><br />[Vergleichsausdrücke](../match-expressions.md)|<ul><li>Begrenzt bei Funktionstypen die Argumente und Rückgabewerte.<br /></li><li>Ergibt einen Ausdruck (in Sequenzausdrücken); entspricht dem `yield`-Schlüsselwort.<br /></li><li>Wird in Übereinstimmungsausdrücken verwendet.<br /></li></ul>|
|`.`|[Mitglieder](../members/index.md)<br /><br />[Primitive Typen](../basic-types.md)|<ul><li>Greift auf einen Member zu und trennt einzelne Namen in einem vollqualifizierten Namen.<br /></li><li>Gibt ein Dezimaltrennzeichen in Gleitkommazahlen an.<br /></li></ul>|
|`..`|[Schleifen: `for...in`-Ausdruck](../loops-for-in-expression.md)|<ul><li>Gibt einen Bereich an.<br /></li></ul>|
|`.. ..`|[Schleifen: `for...in`-Ausdruck](../loops-for-in-expression.md)|<ul><li>Gibt einen Bereich zusammen mit einem Inkrement an.<br /></li></ul>|
|`.[...]`|[Arrays](../arrays.md)|<ul><li>Greift auf ein Arrayelement zu.<br /></li></ul>|
|`/`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)<br /><br />[Maßeinheiten](../units-of-measure.md)|<ul><li>Dividiert die linke Seite (Zähler) durch die rechte Seite (Nenner).<br /></li><li>Wird in Maßeinheittypen verwendet.<br /></li></ul>|
|`/?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Dividiert die linke Seite durch die rechte, wenn die rechte Seite ein Typ ist, der Null-Werte zulässt.<br /></li></ul>|
|`//`||<ul><li>Gibt den Anfang eines einzeiligen Kommentars an.<br /></li></ul>|
|`///`|[XML-Dokumentation](../xml-documentation.md)|<ul><li>Gibt einen XML-Kommentar an.<br /></li></ul>|
|`:`|[Funktionen](../functions/index.md)|<ul><li>Trennt in einer Typanmerkung einen Parameter- oder Membernamen vom Typ.<br /></li></ul>|
|`::`|[Listen](../lists.md)<br /><br />[Vergleichsausdrücke](../match-expressions.md)|<ul><li>Erstellt eine Liste. Das Element auf der linken Seite wird der Liste auf der rechten Seite vorangestellt.<br /></li><li>Wird im Musterabgleich verwendet, um die Teile einer Liste zu trennen.<br /></li></ul>|
|`:=`|[Referenzzellen](../reference-cells.md)|<ul><li>Weist einer Verweiszelle einen Wert zu.<br /></li></ul>|
|`:>`|[Umwandlung und Konvertierungen](../casting-and-conversions.md)|<ul><li>Konvertiert einen Typen in einen Typen, der in der Hierarchie höher ist.<br /></li></ul>|
|`:?`|[Vergleichsausdrücke](../match-expressions.md)|<ul><li>Gibt `true` zurück, wenn der Wert dem angegebenen Typ (oder Untertyp) entspricht, andernfalls `false`<br /></li></ul>|
|`:?>`|[Umwandlung und Konvertierungen](../casting-and-conversions.md)|<ul><li>Konvertiert einen Typen in einen Typen, der in der Hierarchie weiter unten ist.<br /></li></ul>|
|`;`|[Ausführliche Syntax](../verbose-syntax.md)<br /><br />[Listen](../lists.md)<br /><br />[Datensätze](../records.md)|<ul><li>Trennt Ausdrücke (meist in ausführlicher Syntax verwendet).<br /></li><li>Trennt Elemente einer Liste.<br /></li><li>Trennt Felder eines Datensatzes.<br /></li></ul>|
|`<`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)|<ul><li>Berechnet die Kleiner-als-Operation.<br /></li></ul>|
|`<?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|Berechnet die "kleiner als"-Operation, wenn die rechte Seite ein Typ ist, der einen Null-Wert zulässt.|
|`<<`|[Funktionen](../functions/index.md)|<ul><li>Verfasst zwei Funktionen in umgekehrter Reihenfolge, d. h., die zweite Funktion wird zuerst ausgeführt (Rückwärtskompositionsoperator).<br /></li></ul>|
|`<<<`|[Bitwise Operators (Bitweise Operatoren)](bitwise-operators.md)|<ul><li>Verschiebt Bits in der Menge auf der linken Seite um die Anzahl der Bits nach links, die auf der rechten Seite angegeben wurde.<br /></li></ul>|
|`<-`|[Werte](../values/index.md)|<ul><li>Weist einer Variablen einen Wert zu.<br /></li></ul>|
|`<...>`|[Automatische Verallgemeinerung](../generics/automatic-generalization.md)|<ul><li>Begrenzt Typparameter.<br /></li></ul>|
|`<>`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)|<ul><li>Gibt `true` zurück, wenn die linke Seite nicht gleich der rechten Seite ist; andernfalls wird "false" zurückgegeben.<br /></li></ul>|
|`<>?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Berechnet die "nicht gleich"-Operation, wenn die rechte Seite ein Typ ist, der Null-Werte zulässt.<br /></li></ul>|
|`<=`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)|<ul><li>Gibt `true` zurück, wenn die linke Seite kleiner gleich die rechte Seite ist; andernfalls wird `false` zurückgegeben.<br /></li></ul>|
|`<=?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Berechnet die "kleiner gleich"-Operation, wenn die rechte Seite ein Typ ist, der Null-Werte zulässt.<br /></li></ul>|
|<code>&#124;></code>|[Funktionen](../functions/index.md)|<ul><li>Übergibt das Ergebnis der linken Seite an die Funktion auf der rechten Seite (Vorwärtspipeoperator).<br /></li></ul>|
|<code>&#124;&#124;></code>|[&#40; &#124;&#124;&#62; &#41;&#60;'T1,'T2,'U&#62; Funktion](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#(%20%7C%7C%3E%20))|<ul><li>Übergibt das Tupel aus zwei Argumenten auf der linken Seite an die Funktion auf der rechten Seite.<br /></li></ul>|
|<code>&#124;&#124;&#124;></code>|[&#40; &#124;&#124;&#124;&#62; &#41;&#60;'T1,'T2,'T3,'U&#62; Funktion](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#(%20%7C%7C%7C%3E%20))|<ul><li>Übergibt das Tupel aus drei Argumenten auf der linken Seite an die Funktion auf der rechten Seite.<br /></li></ul>|
|<code>&lt;&#124;</code>|[Funktionen](../functions/index.md)|<ul><li>Übergibt das Ergebnis des Ausdrucks auf der rechten Seite an die Funktion auf der linken Seite (Rückwärtspipeoperator).<br /></li></ul>|
|<code>&lt;&#124;&#124;</code>|[&#40; &#60;&#124;&#124; &#41;&#60;'T1,'T2,'U&#62; Funktion](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#(%20%3C%7C%7C%20))|<ul><li>Übergibt das Tupel aus zwei Argumenten auf der rechten Seite an die Funktion auf der linken Seite.<br /></li></ul>|
|<code>&lt;&#124;&#124;&#124;</code>|[&#40; &#60;&#124;&#124;&#124; &#41;&#60;'T1,'T2,'T3,'U&#62; Funktion](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-operators.html#(%20%3C%7C%7C%7C%20))|<ul><li>Übergibt das Tupel aus drei Argumenten auf der rechten Seite an die Funktion auf der linken Seite.<br /></li></ul>|
|`<@...@>`|[Zitieren von Code](../code-quotations.md)|<ul><li>Begrenzt eine typisierte Codequotation.<br /></li></ul>|
|`<@@...@@>`|[Zitieren von Code](../code-quotations.md)|<ul><li>Begrenzt eine nicht typisierte Codequotation.<br /></li></ul>|
|`=`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)|<ul><li>Gibt `true` zurück, wenn die linke Seite gleich der rechten Seite ist; andernfalls wird `false` zurückgegeben.<br /></li></ul>|
|`=?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Berechnet die "gleich"-Operation, wenn die rechte Seite ein Typ ist, der Null-Werte zulässt.<br /></li></ul>|
|`==`||<ul><li>Nicht in F# verwendet. Verwenden Sie `=` für Gleichheitsoperationen.<br /></li></ul>|
|`>`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)|<ul><li>Gibt `true` zurück, wenn die linke Seite größer als die rechte Seite ist; andernfalls wird `false` zurückgegeben.<br /></li></ul>|
|`>?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Berechnet den Größer-als-Vorgang, wenn die rechte Seite ein Nullable-Typ ist<br /></li></ul>|
|`>>`|[Funktionen](../functions/index.md)|<ul><li>Verfasst zwei Funktionen (Vorwärtskompositionsoperator).<br /></li></ul>|
|`>>>`|[Bitwise Operators (Bitweise Operatoren)](bitwise-operators.md)|<ul><li>Verschiebt Bits in der Menge auf der linken Seite um die Anzahl der Bits nach rechts, die auf der rechten Seite angegeben wurde.<br /></li></ul>|
|`>=`|[Arithmetic Operators (Arithmetische Operatoren)](arithmetic-operators.md)|<ul><li>Gibt `true` zurück, wenn die linke Seite größer gleich der rechte Seite ist, andernfalls `false`<br /></li></ul>|
|`>=?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Berechnet die "größer gleich"-Operation, wenn die rechte Seite ein Typ ist, der Null-Werte zulässt.<br /></li></ul>|
|`?`|[Parameter und Argumente](../parameters-and-arguments.md)|<ul><li>Gibt ein optionales Argument an.<br /></li><li>Wird als Operator für dynamische Methoden- und Eigenschaftenaufrufe verwendet. Sie müssen Ihre eigene Implementierung bereitstellen.<br /></li></ul>|
|`? ... <- ...`||<ul><li>Wird als Operator zum Festlegen von dynamischen Eigenschaften verwendet. Sie müssen Ihre eigene Implementierung bereitstellen.<br /></li></ul>|
|`?>=`, `?>`, `?<=`, `?<`, `?=`, `?<>`, `?+`, `?-`, `?*`, `?/`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Entspricht den jeweiligen Operatoren ohne das ? Präfix, wobei sich links ein Typ befindet, der Null-Werte zulässt.<br /></li></ul>|
|`>=?`, `>?`, `<=?`, `<?`, `=?`, `<>?`, `+?`, `-?`, `*?`, `/?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Entspricht den jeweiligen Operatoren ohne das ? Suffix, wobei sich rechts ein Typ befindet, der Null-Werte zulässt.<br /></li></ul>|
|`?>=?`, `?>?`, `?<=?`, `?<?`, `?=?`, `?<>?`, `?+?`, `?-?`, `?*?`, `?/?`|[Operatoren, die NULL-Werte zulassen](nullable-operators.md)|<ul><li>Entspricht den jeweiligen Operatoren ohne die umgebenden Fragezeichen, wobei sich auf beiden Seiten Typen befinden, die Null-Werte zulassen.<br /></li></ul>|
|`@`|[Listen](../lists.md)<br /><br />[Zeichenfolgen](../strings.md)|<ul><li>Verkettet zwei Listen.<br /></li><li>Wenn es vor einem Zeichenfolgenliteral platziert wird, gibt dies an, dass die Zeichenfolge wörtlich interpretiert werden kann, ohne die Escapezeichen zu interpretieren.<br /></li></ul>|
|`[...]`|[Listen](../lists.md)|<ul><li>Begrenzt die Elemente einer Liste.<br /></li></ul>|
|<code>[&#124;...&#124;]</code>|[Arrays](../arrays.md)|<ul><li>Begrenzt die Elemente eines Arrays.<br /></li></ul>|
|`[<...>]`|[Attribute](../attributes.md)|<ul><li>Begrenzt ein Attribut.<br /></li></ul>|
|`\`|[Zeichenfolgen](../strings.md)|<ul><li>Versieht das nächste Zeichen mit einem Escapezeichen; wird in Zeichen- und Zeichenfolgenliteralen verwendet.<br /></li></ul>|
|`^`|[Statisch aufgelöste Typparameter](../generics/statically-resolved-type-parameters.md)<br /><br />[Zeichenfolgen](../strings.md)|<ul><li>Gibt die Typparameter an, die zum Zeitpunkt der Kompilierung, nicht zur Laufzeit aufgelöst werden müssen.<br /></li><li>Verkettet Zeichenfolgen.<br /></li></ul>|
|`^^^`|[Bitwise Operators (Bitweise Operatoren)](bitwise-operators.md)|<ul><li>Berechnet die bitweise XOR-Operation.<br /></li></ul>|
|`_`|[Vergleichsausdrücke](../match-expressions.md)<br /><br />[Generics](../generics/index.md)|<ul><li>Gibt ein Platzhaltermuster an.<br /></li><li>Gibt einen anonymen generischen Parameter an.<br /></li></ul>|
|<code>&#96;</code>|[Automatische Verallgemeinerung](../generics/automatic-generalization.md)|<ul><li>Wird intern verwendet, um einen generischen Typparameter anzugeben.<br /></li></ul>|
|`{...}`|[Sequenzen](../sequences.md)<br /><br />[Datensätze](../records.md)|<ul><li>Begrenzt Sequenzausdrücke und Berechnungsausdrücke.<br /></li><li>Wird in Datensatzdefinitionen verwendet.<br /></li></ul>|
|<code>&#124;</code>|[Vergleichsausdrücke](../match-expressions.md)|<ul><li>Begrenzt einzelne Übereinstimmungsfälle, einzelne diskriminierte Union-Fälle und Enumerationswerte.<br /></li></ul>|
|<code>&#124;&#124;</code>|[Boolesche Operatoren](boolean-operators.md)|<ul><li>Berechnet die boolesche OR-Operation.<br /></li></ul>|
|<code>&#124;&#124;&#124;</code>|[Bitwise Operators (Bitweise Operatoren)](bitwise-operators.md)|<ul><li>Berechnet die bitweise OR-Operation.<br /></li></ul>|
|`~~`|[Operatorüberladung](../operator-overloading.md)|<ul><li>Wird verwendet, um eine Überladung für den unären Negationsoperator zu deklarieren.<br /></li></ul>|
|`~~~`|[Bitwise Operators (Bitweise Operatoren)](bitwise-operators.md)|<ul><li>Berechnet die bitweise NOT-Operation.<br /></li></ul>|
|`~-`|[Operatorüberladung](../operator-overloading.md)|<ul><li>Wird verwendet, um eine Überladung für den unären Minusoperator zu deklarieren.<br /></li></ul>|
|`~+`|[Operatorüberladung](../operator-overloading.md)|<ul><li>Wird verwendet, um eine Überladung für den unären Plusoperator zu deklarieren.<br /></li></ul>|

## <a name="operator-precedence"></a>Operatorrangfolge

Die folgende Tabelle zeigt die Rangreihenfolge der Operatoren und anderer Ausdrucksschlüsselwörter in der F#-Sprache, von der niedrigsten Rangfolge bis zur höchsten Rangfolge. Ggf. wird auch die Assoziativität aufgeführt.

|Betreiber|Assoziativität|
|--------|-------------|
|`as`|Right|
|`when`|Right|
|<code>&#124;</code> (pipe)|Left|
|`;`|Right|
|`let`|Nicht assoziativ|
|`function`, `fun`, `match`, `try`|Nicht assoziativ|
|`if`|Nicht assoziativ|
|`not`|Right|
|`->`|Right|
|`:=`|Right|
|`,`|Nicht assoziativ|
|`or`, <code>&#124;&#124;</code>|Left|
|`&`, `&&`|Left|
|`:>`, `:?>`|Right|
|`<`*op*, `>`*op*, `=`, <code>&#124;</code>*op*, `&`*op*, `&`<br /><br />(einschließlich `<<<`, `>>>`, <code>&#124;&#124;&#124;</code>, `&&&`)|Left|
|`^`*op*<br /><br />(einschließlich `^^^`)|Right|
|`::`|Right|
|`:?`|Nicht assoziativ|
|`-`*op*, `+`*op*|Gilt für infix-Verwendung dieser Symbole|
|`*`*op*, `/`*op*, `%`*op*|Left|
|`**`*op*|Right|
|`f x` (Funktionsanwendung)|Left|
|<code>&#124;</code> (Musterübereinstimmung)|Right|
|Präfixoperatoren (`+`*op*, `-`*op*, `%`, `%%`, `&`, `&&`, `!`*op*, `~`*op*)|Left|
|`.`|Left|
|`f(x)`|Left|
|`f<`*Typen*`>`|Left|

F# unterstützt die benutzerdefinierte Operatorüberladung. Dies bedeutet, dass Sie eigene Operatoren definieren können. In der vorherigen Tabelle kann *op* eine beliebige gültige (möglicherweise leere) Sequenz von integrierten oder benutzerdefinierten Operatorzeichen sein. Mit dieser Tabelle können Sie daher bestimmen, welche Sequenz von Zeichen für einen benutzerdefinierten Operator verwendet werden muss, um die gewünschte Rangfolge zu erhalten. Vorangestellte `.`-Zeichen werden ignoriert, wenn der Compiler die Rangfolge bestimmt.

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](../index.md)
- [Operatorüberladung](../operator-overloading.md)
