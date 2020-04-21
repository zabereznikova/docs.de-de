---
title: Richtlinien für das Formatieren von F#-Code
description: Erfahren Sie mehr über Richtlinien zum Formatieren von F-Code.
ms.date: 11/04/2019
ms.openlocfilehash: b8be70dd29a04e71614308164e541b99a1724305
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739558"
---
# <a name="f-code-formatting-guidelines"></a>Richtlinien für das Formatieren von F#-Code

Dieser Artikel enthält Richtlinien zum Formatieren des Codes, sodass der F-Code:

* Lesbarer
* In Übereinstimmung mit konventionen, die von Formatierungstools in Visual Studio und anderen Editoren angewendet werden
* Ähnlich wie bei anderen Online-Code

Diese Richtlinien basieren auf [einem umfassenden Leitfaden zu den Richtlinien](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) von [Anh-Dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Allgemeine Regeln für den Einzug

Standardmäßig wird ein erheblicher Leerraum verwendet. Die folgenden Richtlinien sollen Anleitungen geben, wie man mit einigen Herausforderungen jonglieren kann, die dies mit sich bringen kann.

### <a name="using-spaces"></a>Verwenden von Räumen

Wenn einEinzug erforderlich ist, müssen Sie Leerzeichen und keine Registerkarten verwenden. Mindestens ein Leerzeichen ist erforderlich. Ihre Organisation kann Codierungsstandards erstellen, um die Anzahl der Leerzeichen anzugeben, die für den Einzug verwendet werden sollen. Zwei, drei oder vier Einrückungsräume auf jeder Ebene, auf der der Einzug stattfindet, sind typisch.

**Wir empfehlen vier Leerzeichen pro Einzug.**

Das heißt, die Einrückung von Programmen ist eine subjektive Angelegenheit. Variationen sind in Ordnung, aber die erste Regel, der Sie folgen sollten, ist *die Konsistenz der Einrückung*. Wählen Sie einen allgemein akzeptierten Einzugsstil und verwenden Sie ihn systematisch in der gesamten Codebasis.

## <a name="formatting-white-space"></a>Formatieren von Leerzeichen

Der Leerraum ist leer. Obwohl die meisten Semantik aus dem weißen Raum durch richtige Einzug abgedeckt sind, gibt es einige andere Dinge zu berücksichtigen.

### <a name="formatting-operators-in-arithmetic-expressions"></a>Formatieren von Operatoren in arithmetischen Ausdrücken

Verwenden Sie immer Leerraum um binäre arithmetische Ausdrücke:

```fsharp
let subtractThenAdd x = x - 1 + 3
```

Unäre `-` Operatoren sollten immer sofort von dem Wert gefolgt werden, den sie negieren:

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

Das Hinzufügen eines Leerzeichens nach dem `-` Operator kann zu Verwechslungen für andere führen.

Zusammenfassend ist es wichtig, immer:

* Umgeben von binären Operatoren mit Leerzeichen
* Niemals nach einem unären Operator nachgelassenen Leerraum haben

Die binäre arithmetische Operator-Richtlinie ist besonders wichtig. Wenn ein binärer `-` Operator nicht mit bestimmten Formatierungsoptionen verbunden ist, `-`kann dies dazu führen, dass er als unär interpretiert wird.

### <a name="surround-a-custom-operator-definition-with-white-space"></a>Umgeben einer benutzerdefinierten Operatordefinition mit Leerraum

Verwenden Sie immer Leerraum, um eine Operatordefinition zu umgeben:

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

Für jeden benutzerdefinierten `*` Operator, der mit mehr als einem Zeichen beginnt und mehr als ein Zeichen enthält, müssen Sie am Anfang der Definition ein Leerzeichen hinzufügen, um eine Compilermehrdeutigkeit zu vermeiden. Aus diesem Grund empfehlen wir, dass Sie einfach die Definitionen aller Operatoren mit einem einzelnen Leerzeichen umgeben.

### <a name="surround-function-parameter-arrows-with-white-space"></a>Surround-Funktionsparameterpfeile mit Leerraum

Verwenden Sie beim Definieren der Signatur einer `->` Funktion Leerzeichen um das Symbol:

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>Surround-Funktionsargumente mit Leerraum

Verwenden Sie beim Definieren einer Funktion Leerraum um jedes Argument.

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a>Platzieren von Parametern in einer neuen Zeile für lange Elementdefinitionen

Wenn Sie über eine sehr lange Elementdefinition verfügen, platzieren Sie die Parameter in neuen Zeilen, und ziehen Sie sie in einen Bereich ein.

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

Dies gilt auch für Konstruktoren:

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a>Typanmerkungen

#### <a name="right-pad-function-argument-type-annotations"></a>Rechts-Pad-Funktionsargumenttyp-Anmerkungen

Verwenden Sie beim Definieren von Argumenten mit `:` Typanmerkungen Leerzeichen nach dem Symbol:

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>Surround-Rückgabetyp-Anmerkungen mit Leerraum

Verwenden Sie in einer let-bound-Funktion oder Werttypanmerkung (Rückgabetyp im Fall `:` einer Funktion) Leerzeichen vor und nach dem Symbol:

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a>Formatieren leerer Zeilen

* Trennen Sie Funktions- und Klassendefinitionen der obersten Ebene mit zwei leeren Zeilen.
* Methodendefinitionen innerhalb einer Klasse werden durch eine einzelne leere Zeile getrennt.
* Zusätzliche leere Zeilen können (sparsam) verwendet werden, um Gruppen verwandter Funktionen zu trennen. Leere Linien können zwischen einer Reihe verwandter Einzeiler weggelassen werden (z. B. eine Reihe von Dummy-Implementierungen).
* Verwenden Sie leere Zeilen in Funktionen sparsam, um logische Abschnitte anzugeben.

## <a name="formatting-comments"></a>Formatieren von Kommentaren

Im Allgemeinen bevorzugen Sie mehrere Doppelschrägstrich-Kommentare gegenüber Blockkommentaren im ML-Stil.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

Inlinekommentare sollten den ersten Buchstaben großschreiben.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Namenskonventionen

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Verwenden von camelCase für klassengebundene, ausdrucks- und mustergebundene Werte und Funktionen

Es ist üblich und akzeptiert Erdstil, camelCase für alle Namen zu verwenden, die als lokale Variablen oder in Musterübereinstimmungen und Funktionsdefinitionen gebunden sind.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Lokal gebundene Funktionen in Klassen sollten auch camelCase verwenden.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Verwenden von camelCase für modulgebundene öffentliche Funktionen

Wenn eine modulgebundene Funktion Teil einer öffentlichen API ist, sollte sie camelCase verwenden:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Verwenden von camelCase für interne und private modulgebundene Werte und Funktionen

Verwenden Sie camelCase für private Modul-gebundene Werte, einschließlich der folgenden:

* Ad-hoc-Funktionen in Skripten

* Werte, aus der die interne Implementierung eines Moduls oder Typs besteht

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>CamelCase für Parameter verwenden

Alle Parameter sollten camelCase gemäß .NET-Namenskonventionen verwenden.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>PascalCase für Module verwenden

Alle Module (top-level, internal, private, nested) sollten PascalCase verwenden.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>PascalCase für Typdeklarationen, Member und Beschriftungen verwenden

Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und diskriminierte Unions sollten alle mit PascalCase benannt werden. Member innerhalb von Typen und Bezeichnungen für Datensätze und diskriminierte Gewerkschaften sollten auch PascalCase verwenden.

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>PascalCase für Konstrukte verwenden, die .NET intrinsisch sind

Namespaces, Ausnahmen, Ereignisse und`.dll` Projektnamen sollten auch PascalCase verwenden. Dadurch fühlt sich der Verbrauch aus anderen .NET-Sprachen für Verbraucher nicht nur natürlicher an, sondern steht auch im Einklang mit .NET-Namenskonventionen, auf die Sie wahrscheinlich stoßen werden.

### <a name="avoid-underscores-in-names"></a>Unterstriche in Namen vermeiden

In der Vergangenheit haben einige F-Bibliotheken Unterstriche in Namen verwendet. Dies wird jedoch nicht mehr allgemein akzeptiert, auch weil es mit .NET-Namenskonventionen kollidiert. Das heißt, einige F-Programmierer verwenden unterstrichen stark, teilweise aus historischen Gründen, und Toleranz und Respekt ist wichtig. Beachten Sie jedoch, dass der Stil von anderen, die eine Wahl haben, ob sie ihn verwenden möchten, oft nicht gemocht wird.

Eine Ausnahme bildet die Zusammenarbeit mit systemeigenen Komponenten, bei denen Unterstriche üblich sind.

### <a name="use-standard-f-operators"></a>Verwenden von Standard-Operatoren für Die Verwendung von F-Operatoren

Die folgenden Operatoren sind in der F-Standardbibliothek definiert und sollten verwendet werden, anstatt Äquivalente zu definieren. Die Verwendung dieser Operatoren wird empfohlen, da Code tendenziell lesbarer und idiomatischer wird. Entwickler mit einem Hintergrund in OCaml oder einer anderen funktionalen Programmiersprache können an verschiedene Idiome gewöhnt sein. In der folgenden Liste werden die empfohlenen F-Operatoren zusammengefasst.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Präfixsyntax für Generika`Foo<T>`verwenden ( ) vorgeben der Postfixsyntax (`T Foo`)

F- erbt sowohl den postfix-ML-Stil des `int list`Namens generischer Typen (z. B. `list<int>`) als auch das Präfix .NET-Stil (z. B. ). Bevorzugen Sie den .NET-Stil, mit Ausnahme von fünf bestimmten Typen:

1. Verwenden Sie für F-Listen das `int list` postfix-Formular: anstelle von `list<int>`.
2. Verwenden Sie für Die Optionen das `int option` postfix-Formular: anstelle von `option<int>`.
3. Verwenden Sie für die Wertoptionen von `int voption` F- Wert das postfix-Formular: anstelle von `voption<int>`.
4. Verwenden Sie für Die Arrays `int[]` den `int array` syntaktischen Namen anstelle von oder `array<int>`.
5. Verwenden Sie `int ref` für Referenzzellen anstelle von `ref<int>` oder `Ref<int>`.

Verwenden Sie für alle anderen Typen das Präfixformular.

## <a name="formatting-tuples"></a>Formatieren von Tupeln

Eine Tupelinstanziierung sollte in Klammern sein, und auf die darin abschnittnden begrenzenden `(1, 2)` `(x, y, z)`Kommas sollte ein einzelnes Leerzeichen folgen, z. B.: .

Es ist allgemein akzeptiert, Klammern in Muster-Matching von Tupeln wegzulassen:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

Es ist auch allgemein akzeptiert, Klammern wegzulassen, wenn das Tupel der Rückgabewert einer Funktion ist:

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

Zusammenfassend ist, dass die Parenthesized Tupelinstanziationen bevorzugt werden, aber wenn Sie Tupel für Musterabgleich oder einen Rückgabewert verwenden, gilt es als fein, Klammern zu vermeiden.

## <a name="formatting-discriminated-union-declarations"></a>Formatieren diskriminierter Gewerkschaftserklärungen

Einzug `|` in Typdefinition durch vier Leerzeichen:

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a>Formatieren diskriminierter Gewerkschaften

Instanziierte diskriminierte Unions, die sich über mehrere Zeilen verteilen, sollten enthaltenen Daten einen neuen Bereich mit Einzug geben:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

Die schließende Klammer kann sich auch auf einer neuen Linie befinden:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Formatieren von Datensatzdeklarationen

Einrücken `{` in Typdefinition durch vier Leerzeichen und starten Sie die Feldliste in derselben Zeile:

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

Das Platzieren des öffnenden Tokens in einer neuen Zeile und des schließenden Tokens in einer neuen Zeile ist vorzuziehen, wenn Sie Schnittstellenimplementierungen oder Member im Datensatz deklarieren:

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a>Formatieren von Datensätzen

Kurze Datensätze können in einer Zeile geschrieben werden:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Datensätze, die länger sind, sollten neue Zeilen für Beschriftungen verwenden:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Das Platzieren des Öffnenstokens in einer neuen Zeile, das Tabbed des Inhalts über einen Bereich und das schließende Token in einer neuen Zeile ist vorzuziehen, wenn Sie:

* Verschieben von Datensätzen im Code mit unterschiedlichen Einzugsbereichen
* Sie in eine Funktion einzupfeifen

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

Für Listen- und Arrayelemente gelten die gleichen Regeln.

## <a name="formatting-copy-and-update-record-expressions"></a>Formatieren von Kopier- und Aktualisierungsdatensatzausdrücken

Ein Copy-and-Update-Datensatzausdruck ist immer noch ein Datensatz, daher gelten ähnliche Richtlinien.

Kurze Ausdrücke können in eine Zeile passen:

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

Längere Ausdrücke sollten neue Zeilen verwenden:

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Wie bei der Datensatzanleitung können Sie separate Zeilen für die geschweiften Klammern und einEinzug eines Bereichs nach rechts mit dem Ausdruck widmen. In einigen speziellen Fällen, z. B. beim Umschließen eines Werts mit einem optionalen Wert ohne Klammern, müssen Sie möglicherweise eine geschweifte Klammer in einer Zeile beibehalten:

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a>Formatieren von Listen und Arrays

Schreiben `x :: l` Sie mit `::` Leerzeichen um den Operator (ist`::` ein Infixoperator, daher von Leerzeichen umgeben).

Liste und Arrays, die in einer einzelnen Zeile deklariert sind, sollten ein Leerzeichen nach der öffnenden Klammer und vor der schließenden Klammer haben:

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen, koredagen Operatoren. Lassen Sie z. B. ein Leerzeichen zwischen a `[` und a. `{`

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

Die gleiche Richtlinie gilt für Listen oder Arrays von Tupeln.

Listen und Arrays, die über mehrere Zeilen aufgeteilt sind, folgen einer ähnlichen Regel wie Datensätze:

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

Und wie bei Datensätzen erleichtert das Deklarieren der öffnenden und schließenden Klammern in ihrer eigenen Zeile das Verschieben von Code und das Einleiten in Funktionen.

Wenn Arrays und Listen programmgesteuert `->` generiert `do ... yield` werden, bevorzugen Sie, wenn immer ein Wert generiert wird:

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

In Situationen, `yield` in denen Daten bedingt generiert werden können oder aufeinander folgende Ausdrücke ausgewertet werden müssen, sind ältere Versionen der Sprache "F" erforderlich. Bevorzugen Sie das `yield` Weglassen dieser Schlüsselwörter, es sei denn, Sie müssen mit einer älteren Version der F-Sprache kompilieren:

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

In einigen `do...yield` Fällen kann dies zur Lesbarkeit beiderbarkeit s. Diese Fälle sind zwar subjektiv, sollten aber berücksichtigt werden.

## <a name="formatting-if-expressions"></a>Formatieren von Ausdrücken

Der Einzug von Conditionals hängt von der Größe der Ausdrücke ab, aus denen sie besteht. Wenn `cond` `e1` , `e2` und kurz sind, schreiben Sie sie einfach in einer Zeile:

```fsharp
if cond then e1 else e2
```

Wenn `cond`entweder `e1` `e2` , oder länger, aber nicht mehrzeilig:

```fsharp
if cond
then e1
else e2
```

Wenn einer der Ausdrücke mehrzeilige Ausdrücke ist:

```fsharp
if cond then
    e1
else
    e2
```

Mehrere Conditionals `elif` `else` mit und werden im gleichen `if`Bereich wie die eingerückt:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Musterübereinstimmungskonstrukte

Verwenden `|` Sie für jede Klausel einer Übereinstimmung ohne Einzug eine. Wenn der Ausdruck kurz ist, können Sie eine einzelne Zeile verwenden, wenn jeder Unterausdruck ebenfalls einfach ist.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

Wenn der Ausdruck auf der rechten Seite des Musterübereinstimmungspfeils zu groß ist, `match` / `|`verschieben Sie ihn in die folgende Zeile, die einen Schritt von der eingerückt wird.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Der Musterabgleich anonymer `function`Funktionen, beginnend mit , sollte in der Regel nicht zu weit einrücken. Beispielsweise ist es in Ordnung, einen Bereich wie folgt einzuablehnen:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Musterabgleich in `let` Funktionen, die von vier Leerzeichen definiert sind oder `let rec` nach dem Start von `let`eingerückt werden sollen, auch wenn `function` das Schlüsselwort verwendet wird:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Es wird nicht empfohlen, die Pfeile auszurichten.

## <a name="formatting-trywith-expressions"></a>Formatieren try/with-Ausdrücke

Der Musterabgleich für den Ausnahmetyp sollte auf `with`derselben Ebene wie eingerückt werden.

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a>Formatierungsfunktion ParameterAnwendung

Im Allgemeinen wird die Anwendung der meisten Funktionsparameter in derselben Zeile durchgeführt.

Wenn Sie Parameter auf eine Funktion in einer neuen Zeile anwenden möchten, ziehen Sie sie um einen Bereich ein.

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

Dieselben Richtlinien gelten für Lambda-Ausdrücke als Funktionsargumente. Wenn der Körper eines Lambda-Ausdrucks, kann der Körper eine andere Linie haben, eingerückt durch einen Bereich

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

Wenn der Text eines Lambdaausdrucks jedoch mehr als eine Zeile ist, sollten Sie ihn in eine separate Funktion einteilen, anstatt ein mehrzeiliges Konstrukt als einzelnes Argument auf eine Funktion anzuwenden.

### <a name="formatting-infix-operators"></a>Formatieren von Infixoperatoren

Trennen Sie Operatoren nach Leerzeichen. Offensichtliche Ausnahmen von dieser `!` Regel `.` sind die und Operatoren.

Infix-Ausdrücke sind INfix-Auflisten in derselben Spalte:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Formatieren von Pipelineoperatoren

Pipeline-Operatoren `|>` sollten sich unter die Ausdrücke befolgen, auf denen sie arbeiten.

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a>Formatieren von Modulen

Code in einem lokalen Modul muss relativ zum Modul eingerückt werden, code in einem Modul der obersten Ebene sollte jedoch nicht eingerückt werden. Namespaceelemente müssen nicht eingerückt werden.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a>Formatieren von Objektausdrücken und -schnittstellen

Objektausdrücke und -schnittstellen sollten auf die `member` gleiche Weise ausgerichtet werden, wenn sie nach vier Leerzeichen eingerückt werden.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Formatieren von Leerraum in Ausdrücken

Vermeiden Sie überflüssige Leerzeichen in F-Ausdrücken.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Benannte Argumente sollten auch `=`keinen Platz für die folgenden Argumente haben:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a>Formatieren von Attributen

[Attribute](../language-reference/attributes.md) werden über einem Konstrukt platziert:

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a>Formatieren von Attributen für Parameter

Attribute können auch Orte auf Parametern sein. Platzieren Sie in diesem Fall dann dieselbe Zeile wie der Parameter und vor dem Namen:

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>Formatieren mehrerer Attribute

Wenn mehrere Attribute auf ein Konstrukt angewendet werden, das kein Parameter ist, sollten sie so platziert werden, dass es ein Attribut pro Zeile gibt:

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

Wenn sie auf einen Parameter angewendet werden, müssen `;` sie sich in derselben Zeile und durch ein Trennzeichen getrennt haben.

## <a name="formatting-literals"></a>Formatieren von Literalen

[Die Definitionen,](../language-reference/literals.md) `Literal` die das Attribut verwenden, sollten das Attribut in einer eigenen Zeile platzieren und die PascalCase-Benennung verwenden:

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

Vermeiden Sie es, das Attribut in derselben Zeile wie der Wert zu platzieren.
