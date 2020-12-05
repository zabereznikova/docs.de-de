---
title: Musterabgleich
description: 'Erfahren Sie, wie Muster in F # verwendet werden, um Daten mit logischen Strukturen zu vergleichen, Daten in Bestandteile zu zerlegen oder Informationen aus Daten zu extrahieren.'
ms.date: 11/12/2020
ms.openlocfilehash: 932f50b7947f6df728149437dd3ceb19c42e5c6a
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740275"
---
# <a name="pattern-matching"></a>Musterabgleich

Muster sind Regeln zum Transformieren von Eingabedaten. Sie werden in F# stets verwendet, um Daten mit logischen Strukturen zu vergleichen, Daten in einzelne Bestandteile zu zerlegen oder auf unterschiedliche Weise Informationen aus Daten zu extrahieren.

## <a name="remarks"></a>Bemerkungen

Muster werden in vielen Sprachkonstrukten verwendet, z. B. im `match`-Ausdruck. Sie werden verwendet, wenn Argumente für Funktionen in `let`-Bindungen oder Lambda-Ausdrücken verarbeitet werden, sowie in den dem `try...with`-Ausdruck zugeordneten Ausnahmehandlern. Weitere Informationen finden Sie unter [Match Expressions](match-expressions.md), [let-Bindungen](./functions/let-bindings.md), [Lambda-Ausdrücke: das `fun` Schlüsselwort](./functions/lambda-expressions-the-fun-keyword.md)und [Ausnahmen: der `try...with` Ausdruck](./exception-handling/the-try-with-expression.md).

Im `match` Ausdruck ist das *Muster* z. b. das, was dem Pipe-Symbol folgt.

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

Jedes Muster fungiert als Regel zum Transformieren von Eingaben. Im `match`-Ausdruck wird jedes Muster einzeln untersucht, um zu ermitteln, ob die Eingabedaten mit dem Muster kompatibel sind. Wenn eine Übereinstimmung gefunden wird, wird der Ergebnisausdruck ausgeführt. Wenn keine Übereinstimmung gefunden wird, wird die nächste Musterregel getestet. Der *optionale when-* Bedingungs Teil wird in [Match-Ausdrücken](match-expressions.md)erläutert.

In der folgenden Tabelle werden unterstützte Muster aufgeführt. Zur Laufzeit wird die Eingabe anhand jedes der folgenden Muster in der in der Tabelle aufgeführten Reihenfolge überprüft. Die Muster werden rekursiv vom ersten bis zum letzten Muster im Code und von links nach rechts in den einzelnen Zeilen angewendet.

|Name|BESCHREIBUNG|Beispiel|
|----|-----------|-------|
|Konstantenmuster|Ein beliebiges numerisches Literal, Zeichenliteral oder Zeichenfolgenliteral, eine Enumerationskonstante oder ein definierter Literalbezeichner.|`1.0`, `"test"`, `30`, `Color.Red`|
|Bezeichnermuster|Der Wert eines Falls einer Unterscheidungs-Union, eine Ausnahmebezeichnung oder ein Fall eines aktiven Musters.|`Some(x)`<br /><br />`Failure(msg)`|
|Variablenmuster|*identifier*|`a`|
|`as`-Muster|*Muster* als *Bezeichner*|`(a, b) as tuple1`|
|OR-Muster|*muster1* &#124; *muster2*|<code>([h] &#124; [h; _])</code>|
|AND-Muster|*muster1* &amp; *muster2*|`(a, b) & (_, "test")`|
|Cons-Muster|*identifier* *Bezeichner:: List-Identifier*|`h :: t`|
|Listenmuster|[ *pattern_1*;...; *pattern_n* ]|`[ a; b; c ]`|
|Arraymuster|[&#124; *pattern_1*;..; *pattern_n* &#124;]|<code>[&#124; a; b; c &#124;]</code>|
|Muster in Klammern|( *Muster* )|`( a )`|
|Tupelmuster|( *pattern_1*,..., *pattern_n* )|`( a, b )`|
|Datensatzmuster|{ *Bezeichner1*  =  *pattern_1*; ... ; *identifier_n*  =  *pattern_n* }|`{ Name = name; }`|
|Platzhaltermuster|_|`_`|
|Muster zusammen mit Typanmerkung|*Pattern* : *Type*|`a : int`|
|Typtestmuster|:? *Type* [as *Identifier* ]|`:? System.DateTime as dt`|
|NULL-Muster|NULL|`null`|
|Nameof-Muster|*nameof-expr*|`nameof str`|

## <a name="constant-patterns"></a>Konstantenmuster

Konstantenmuster sind numerische Literale, Zeichenliterale und Zeichenfolgenliterale, Enumerationskonstanten (einschließlich Enumerationstypnamen). Ein `match`-Ausdruck, der nur über Konstantenmuster verfügt, ist mit case-Anweisungen in anderen Sprachen vergleichbar. Die Eingabe wird mit dem Literalwert verglichen, und das Muster stimmt überein, wenn die Werte gleich sind. Der Typ des Literals muss mit dem Typ der Eingabe kompatibel sein.

Im folgenden Beispiel wird die Verwendung von Literalmustern veranschaulicht, und es werden außerdem ein Variablenmuster und ein OR-Muster verwendet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

Ein weiteres Beispiel für ein Literalmuster ist ein auf Enumerationskonstanten basierendes Muster. Wenn Sie Enumerationskonstanten verwenden, müssen Sie den Enumerationstypnamen angeben.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a>Bezeichnermuster

Wenn das Muster eine Zeichenfolge ist, die einen gültigen Bezeichner bildet, bestimmt die Form des Bezeichners, wie das Muster verglichen wird. Wenn der Bezeichner länger als ein einzelnes Zeichen ist und mit einem Großbuchstaben beginnt, versucht der Compiler, eine Übereinstimmung mit dem Bezeichnermuster zu ermitteln. Der Bezeichner für dieses Muster kann ein Wert sein, der mit dem Literal-Attribut, einem Unterscheidungs-Union-Fall, einem Ausnahmebezeichner oder einem Fall eines aktiven Musters markiert wurde. Wenn kein übereinstimmender Bezeichner gefunden wird, schlägt der Vergleich fehl, und die nächste Musterregel, das Variablenmuster, wird mit der Eingabe verglichen.

Unterscheidungs-Union-Muster können einfache benannte Fälle sein oder über einen Wert bzw. über ein mehrere Werte enthaltendes Tupel verfügen. Wenn ein Wert vorhanden ist, müssen Sie einen Bezeichner für den Wert angeben. Im Fall eines Tupels müssen Sie ein Tupelmuster mit einem Bezeichner für jedes Element des Tupels oder einen Bezeichner mit einem Feldnamen für eine oder mehrere benannte Union-Felder angeben. Entsprechende Beispiele finden Sie in den Codebeispielen dieses Abschnitts.

Der `option`-Typ ist eine Unterscheidungs-Union mit den beiden Fällen `Some` und `None`. Ein Fall (`Some`) verfügt über einen Wert, der andere Fall (`None`) ist jedoch lediglich ein benannter Fall. Daher muss `Some` über eine Variable für den dem Fall `Some` zugeordneten Wert verfügen, `None` muss jedoch als None angegeben werden. Im folgenden Code wird der Variablen `var1` der Wert zugewiesen, der durch den Vergleich mit dem Fall `Some` ermittelt wurde.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

Im folgenden Beispiel enthält die Unterscheidungs-Union `PersonName` eine Kombination von Zeichenfolgen und Zeichen, die mögliche Formen von Namen darstellen. Die Fälle der Unterscheidungs-Union lauten `FirstOnly`, `LastOnly` und `FirstLast`.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

Für Unterscheidungs-Unions, die über benannte Felder verfügen, verwenden Sie das Gleichheitszeichen (=), um den Wert eines benannten Felds zu extrahieren. Betrachten Sie zum Beispiel eine Unterscheidungs-Union mit einer Deklaration wie der folgenden.

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

Sie können die benannten Felder in einem Musterabgleichsausdruck wie folgt verwenden.

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn $"Rectangle with length %f{h}"
    | Circle(r) -> printfn $"Circle with radius %f{r}"
```

Die Verwendung des benannten Felds ist optional. Im vorherigen Beispiel haben `Circle(r)` und `Circle(radius = r)` die gleiche Auswirkung.

Wenn Sie mehrere Felder angeben, verwenden Sie das Semikolon (;) als Trennzeichen.

```fsharp
match shape with
| Rectangle(height = h; width = w) -> printfn $"Rectangle with height %f{h} and width %f{w}"
| _ -> ()
```

Mit aktiven Mustern können Sie komplexere benutzerdefinierte Musterabgleiche definieren. Weitere Informationen zu aktiven Mustern finden Sie unter [aktive Muster](active-patterns.md).

Der Fall, in dem der Bezeichner eine Ausnahme ist, wird beim Mustervergleich im Kontext von Ausnahmehandlern verwendet. Weitere Informationen zum Musterabgleich bei der Ausnahmebehandlung finden Sie unter [Ausnahmen: der `try...with` Ausdruck](./exception-handling/the-try-with-expression.md).

## <a name="variable-patterns"></a>Variablenmuster

Im Variablenmuster wird dem zu vergleichenden Wert ein Variablenname zugewiesen, der dann im Ausführungsausdruck auf der rechten Seite des Symbols `->` verwendet werden kann. Ein Variablenmuster an sich stimmt mit jeder Eingabe überein, jedoch sind Variablenmuster häufig in anderen Mustern enthalten und ermöglichen somit komplexere Strukturen, z. B. Tupel und Arrays, die in Variablen zerlegt werden sollen.

Im folgenden Beispiel wird ein Variablenmuster in einem Tupelmuster veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a>as-Muster

Das `as`-Muster ist ein Muster, an das eine `as`-Klausel angefügt ist. Die `as`-Klausel bindet den übereinstimmenden Wert an einen Namen, der im Ausführungsausdruck eines `match`-Ausdrucks verwendet werden kann. Falls das Muster in einer `let`-Bindung verwendet wird, wird stattdessen der Name dem lokalen Bereich als Bindung hinzugefügt.

Im folgenden Beispiel wird ein `as`-Muster verwendet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a>OR-Muster

Das OR-Muster wird verwendet, wenn Eingabedaten mit mehreren Mustern übereinstimmen können und als Ergebnis der gleiche Code ausgeführt werden soll. Die Typen beider Seiten des OR-Musters müssen kompatibel sein.

Das OR-Muster wird im folgenden Beispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a>AND-Muster

Das AND-Muster erfordert, dass die Eingabe mit zwei Mustern übereinstimmt. Die Typen beider Seiten des AND-Musters müssen kompatibel sein.

Das folgende Beispiel ist ähnlich wie `detectZeroTuple` im Abschnitt tupelmuster weiter unten in diesem Thema dargestellt. hier werden jedoch sowohl `var1` `var2` als auch Werte mithilfe des-Musters und des-Musters abgerufen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a>Cons-Muster

Das Cons-Muster wird verwendet, um eine Liste in das erste Element, den *Kopf* und eine Liste *mit den restlichen* Elementen, dem Ende, zu zerlegen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a>Listenmuster

Mit dem Listenmuster können Listen in eine Reihe von Elementen zerlegt werden. Das Listenmuster selbst darf nur mit Listen einer bestimmten Anzahl von Elementen übereinstimmen.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a>Arraymuster

Das Arraymuster ähnelt dem Listenmuster, und es kann zum Zerlegen von Arrays einer bestimmten Länge verwendet werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a>Muster in Klammern

Muster können in Klammern eingeschlossen werden, um die gewünschte Assoziativität zu erreichen. Im folgenden Beispiel werden Klammern verwendet, um die Assoziativität zwischen einem AND-Muster und einem Cons-Muster zu steuern.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a>Tupelmuster

Mithilfe des Tupelmusters werden Eingabe in Tupelform verglichen. Es ermöglicht das Zerlegen des Tupels in seine Bestandteile mithilfe von Musterabgleichsvariablen für die einzelnen Positionen im Tupel.

Im folgenden Beispiel wird die Verwendung des Tupelmusters veranschaulicht, und es werden außerdem Literalmuster, Variablenmuster und das Platzhaltermuster verwendet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a>Datensatzmuster

Mit dem Datensatzmuster werden Datensätze zerlegt, um die Werte von Feldern zu extrahieren. Das Muster muss nicht auf alle Felder des Datensatzes verweisen. Weggelassene Felder werden nicht verglichen und nicht extrahiert.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a>Platzhaltermuster

Das Platzhaltermuster wird durch den Unterstrich (`_`) dargestellt und stimmt wie das Variablenmuster mit jeder Eingabe überein, außer dass die Eingabe verworfen wird, anstatt einer Variablen zugewiesen zu werden. Das Platzhaltermuster wird oft innerhalb anderer Muster als Platzhalter für Werte verwendet, die im Ausdruck auf der rechten Seite des Symbols `->` nicht benötigt werden. Das Platzhaltermuster wird außerdem häufig am Ende einer Liste von Mustern als Übereinstimmung für jede nicht übereinstimmende Eingabe verwendet. Das Platzhaltermuster wird in vielen Codebeispielen dieses Themas veranschaulicht. Ein Beispiel finden Sie im vorangehenden Code.

## <a name="patterns-that-have-type-annotations"></a>Muster mit Typanmerkungen

Muster können Typanmerkungen aufweisen. Diese verhalten sich wie andere Typanmerkungen und steuern Typrückschluss wie diese. Typanmerkungen in Mustern müssen in Klammern eingeschlossen werden. Im folgenden Code wird ein Muster veranschaulicht, das eine Typanmerkung aufweist.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a>Typtestmuster

Das Typtestmuster wird verwendet, um die Eingabe anhand eines Typs zu vergleichen. Wenn der Eingabetyp mit dem im Muster angegebenen Typ oder einem von diesem abgeleiteten Typ übereinstimmt, ist der Vergleich erfolgreich.

Das Typtestmuster wird im folgenden Beispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

Wenn Sie nur überprüfen, ob es sich bei einem Bezeichner um einen bestimmten abgeleiteten Typ handelt, benötigen Sie den `as identifier` Teil des Musters nicht, wie im folgenden Beispiel gezeigt:

```fsharp
type A() = class end
type B() = inherit A()
type C() = inherit A()

let m (a: A) =
    match a with
    | :? B -> printfn "It's a B"
    | :? C -> printfn "It's a C"
    | _ -> ()
```

## <a name="null-pattern"></a>NULL-Muster

Das NULL-Muster wird mit dem NULL-Wert verglichen, der beim Arbeiten mit Typen, die NULL-Werte zulassen, vorhanden sein kann. NULL-Muster werden häufig verwendet, wenn Sie mit .NET Framework Code interagieren. Beispielsweise kann der Rückgabewert einer .NET-API die Eingabe für einen `match`-Ausdruck sein. Die Steuerung des Programmablaufs kann von Eigenschaften des Rückgabewerts abhängig gemacht werden, beispielsweise davon, ob der Rückgabewert NULL ist. Mithilfe des NULL-Musters können Sie verhindern, dass NULL-Werte an den Rest des Programms weitergegeben werden.

Im folgenden Beispiel werden das NULL-Muster und das Variablenmuster verwendet.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="nameof-pattern"></a>Nameof-Muster

Das `nameof` Muster entspricht einer Zeichenfolge, wenn sein Wert gleich dem Ausdruck ist, der dem `nameof` Schlüsselwort folgt. Beispiel:

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```

[`nameof`](nameof.md)Informationen dazu, wie Sie einen Namen verwenden können, finden Sie unter dem-Operator.

## <a name="see-also"></a>Weitere Informationen

- [Vergleichsausdrücke](match-expressions.md)
- [Aktive Muster](active-patterns.md)
- [F#-Sprachreferenz](index.md)
