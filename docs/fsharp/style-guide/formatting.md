---
title: Richtlinien für das Formatieren von F#-Code
description: 'Hier finden Sie Richtlinien zum Formatieren von F #'
ms.date: 08/31/2020
ms.openlocfilehash: af98be75f21cbc594ff9cf779561d49e4965845a
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688253"
---
# <a name="f-code-formatting-guidelines"></a>Richtlinien für das Formatieren von F#-Code

Dieser Artikel enthält Richtlinien zum Formatieren von Code, sodass der F #-Code wie folgt lautet:

* Besser lesbar
* In Übereinstimmung mit Konventionen, die von Formatierungs Tools in Visual Studio und anderen Editoren angewendet werden
* Vergleichbar mit anderem Code Online

Diese Richtlinien basieren auf [einer umfassenden Anleitung zu F #-Formatierungs Konventionen](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) durch [Anh-dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Allgemeine Regeln für Einzug

In F # wird standardmäßig signifikanter Leerraum verwendet. Die folgenden Richtlinien dienen als Leitfaden zum vermitteln einiger Herausforderungen, die dies erzwingen kann.

### <a name="using-spaces"></a>Verwenden von Leerzeichen

Wenn Einzug erforderlich ist, müssen Sie Leerzeichen und keine Tabulatoren verwenden. Es ist mindestens ein Leerzeichen erforderlich. In Ihrer Organisation können Codierungsstandards erstellt werden, um die Anzahl der für den Einzug zu verwendenden Leerzeichen anzugeben. zwei, drei oder vier Leerzeichen für den Einzug auf jeder Ebene, in der der Einzug auftritt, ist typisch.

**Es werden vier Leerzeichen pro Einzug empfohlen.**

Dies bedeutet, dass der Einzug von Programmen eine subjektive Angelegenheit ist. Variationen sind in Ordnung, aber die erste Regel, die Sie befolgen sollten, ist die *Konsistenz des* Einzugs. Wählen Sie eine im allgemeinen akzeptierte Art von Einzug aus, und verwenden Sie sie systematisch in der gesamten Codebasis.

## <a name="formatting-white-space"></a>Formatieren von Leerraum

F # ist Leerraum sensibel. Obwohl die meisten Semantik aus Leerraum durch den ordnungsgemäßen Einzug abgedeckt ist, müssen einige andere Punkte berücksichtigt werden.

### <a name="formatting-operators-in-arithmetic-expressions"></a>Formatierungs Operatoren in arithmetischen Ausdrücken

Verwenden Sie immer Leerraum um binäre arithmetische Ausdrücke:

```fsharp
let subtractThenAdd x = x - 1 + 3
```

Unäre `-` Operatoren sollten immer direkt auf den Wert folgen, den Sie neinieren:

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

Wenn ein Leerzeichen nach dem Operator hinzugefügt wird `-` , kann dies zu Verwirrung für andere führen.

Zusammenfassend ist es wichtig, immer Folgendes zu beachten:

* Binäre Operatoren mit Leerraum umschließen
* Nach einem unären Operator nie nachfolgende Leerzeichen enthalten

Die Richtlinie für den binären arithmetischen Operator ist besonders wichtig. Wenn ein binärer Operator nicht umschließt `-` , in Kombination mit bestimmten Formatierungsoptionen, könnte dies dazu führen, dass er als unäres interpretiert wird `-` .

### <a name="surround-a-custom-operator-definition-with-white-space"></a>Umschließen einer benutzerdefinierten Operator Definition mit Leerraum

Verwenden Sie immer Leerraum, um eine Operator Definition zu umschließen:

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

Für alle benutzerdefinierten Operatoren, die mit beginnen `*` und über mehr als ein Zeichen verfügen, müssen Sie am Anfang der Definition ein Leerzeichen hinzufügen, um eine compilermehrdeutigkeit zu vermeiden. Aus diesem Grund wird empfohlen, die Definitionen aller Operatoren einfach mit einem einzelnen Leerzeichen zu umschließen.

### <a name="surround-function-parameter-arrows-with-white-space"></a>Umschließen von Funktionsparameter Pfeilen mit Leerraum

Wenn Sie die Signatur einer Funktion definieren, verwenden Sie Leerraum um das `->` Symbol:

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a>Umschließen von Funktions Argumenten mit Leerraum

Verwenden Sie beim Definieren einer Funktion Leerzeichen um jedes Argument.

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-definitions"></a>Parameter für lange Definitionen in einer neuen Zeile platzieren

Wenn Sie über eine sehr lange Funktionsdefinition verfügen, platzieren Sie die Parameter in neuen Zeilen, und fügen Sie Sie ein, damit Sie der Einzugs Ebene des nachfolgenden Parameters entsprechen.

```fsharp
module M =
    let LongFunctionWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                        =
        // ... the body of the method follows
```

Dies gilt auch für Member, Konstruktoren und Parameter mithilfe von Tupeln:

```fsharp
type TM() =
    member _.LongMethodWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method

type TC(aVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aSecondVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse,
        aThirdVeryLongCtorParam: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

Wenn die Parameter klassifiziert werden oder eine explizite Rückgabetyp Anmerkung vorliegt, ist es vorzuziehen, das `=` Zeichen in einer neuen Zeile zu platzieren:

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                            : AReturnType =
        // ... the body of the method
    member _.LongMethodWithLotsOfCurrifiedParams(aVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                (aSecondVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                (aThirdVeryLongParam: AVeryLongTypeThatYouNeedToUse)
                                                =
        // ... the body of the method
```

Dies ist eine Methode, um zu lange Zeilen zu vermeiden (für den Fall, dass der Rückgabetyp einen langen Namen aufweisen kann) und weniger Zeilen Schaden beim Hinzufügen von Parametern hat

### <a name="type-annotations"></a>Typanmerkungen

#### <a name="right-pad-function-argument-type-annotations"></a>Typanmerkungen für Funktionsargumente des Rechts Auffüll Bereichs

Wenn Sie Argumente mit Typanmerkungen definieren, verwenden Sie Leerraum nach dem `:` Symbol:

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a>Umschließende Rückgabetyp Anmerkungen mit Leerraum

Verwenden Sie in einer Let-gebundenen Funktion oder Werttyp Anmerkung (Rückgabetyp im Fall einer Funktion) Leerraum vor und nach dem `:` Symbol:

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a>Formatieren von leeren Zeilen

* Trennen Sie Funktions-und Klassendefinitionen der obersten Ebene mit zwei leeren Zeilen.
* Methoden Definitionen innerhalb einer Klasse werden durch eine einzelne Leerzeile getrennt.
* Zusätzliche leere Zeilen können (sparsam) zum Trennen von Gruppen verwandter Funktionen verwendet werden. Leere Zeilen können zwischen einer Reihe verwandter Einzeiler (z. b. einer Gruppe von Pseudo Implementierungen) weggelassen werden.
* Verwenden Sie in Funktionen, die in den Funktionen sehr sparsam sind, um logische Abschnitte anzugeben.

## <a name="formatting-comments"></a>Formatieren von Kommentaren

Bevorzugen Sie im Allgemeinen mehrere Kommentare mit doppelten Schrägstrichen über Block Kommentare im ml-Stil.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

Inline Kommentare sollten den ersten Buchstaben ausnutzen.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Namenskonventionen

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Verwenden Sie "CamelCase" für Klassen gebundene, Ausdrucks gebundene und Muster gebundene Werte und Funktionen.

Es ist üblich, dass im F #-Stil für alle Namen, die als lokale Variablen oder in Muster Übereinstimmungen und Funktionsdefinitionen gebunden sind, "CamelCase" verwendet wird.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Lokal gebundene Funktionen in Klassen sollten auch "CamelCase" verwenden.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Verwenden von "CamelCase" für Modul gebundene öffentliche Funktionen

Wenn eine Modul gebundene Funktion Teil einer öffentlichen API ist, sollte Sie "CamelCase" verwenden:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Verwenden Sie "CamelCase" für interne und private Modul gebundene Werte und Funktionen.

Verwenden Sie CamelCase für private Modul gebundene Werte, einschließlich der folgenden:

* Ad-hoc-Funktionen in Skripts

* Werte, die die interne Implementierung eines Moduls oder Typs bilden

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Verwenden Sie "CamelCase" für Parameter.

Alle Parameter sollten in Übereinstimmung mit den .net-Benennungs Konventionen "CamelCase" verwenden.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Verwenden von PascalCase für Module

Alle Module (Top-Level, Internal, private, netsted) sollten PascalCase verwenden.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Verwenden von PascalCase für Typdeklarationen, Elemente und Bezeichnungen

Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und Unterscheidungs-Unions sollten mit PascalCase benannt werden. Member innerhalb von Typen und Bezeichnungen für Datensätze und Unterscheidungs-Unions sollten auch PascalCase verwenden.

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Verwenden von PascalCase für Konstrukte in .net

Namespaces, Ausnahmen, Ereignisse und Projekt/ `.dll` Namen sollten ebenfalls PascalCase verwenden. Dies bedeutet nicht nur, dass die Nutzung von anderen .NET-Sprachen für Consumer natürlicher ist, sondern auch mit den .net-Benennungs Konventionen, die wahrscheinlich auftreten.

### <a name="avoid-underscores-in-names"></a>Unterstriche in Namen vermeiden

In der Vergangenheit haben einige F #-Bibliotheken Unterstriche in Namen verwendet. Dies wird jedoch nicht mehr weitgehend akzeptiert, weil es Konflikte mit .net-Benennungs Konventionen verursacht. Das heißt, einige F #-Programmierer verwenden Unterstriche stark, teilweise aus historischen Gründen, und Toleranz und Respekt ist wichtig. Beachten Sie jedoch, dass der Stil oft von anderen Benutzern nicht gefällt, die entscheiden können, ob diese verwendet werden sollen.

Eine Ausnahme umfasst die Interoperabilität mit systemeigenen Komponenten, bei denen Unterstriche häufig vorkommen.

### <a name="use-standard-f-operators"></a>Standard-F #-Operatoren verwenden

Die folgenden Operatoren sind in der F #-Standardbibliothek definiert und sollten anstelle der Definition von Entsprechungen verwendet werden. Die Verwendung dieser Operatoren wird empfohlen, da Sie dazu führt, dass der Code besser lesbar und idiatisch ist. Entwickler, die einen Hintergrund in ocaml oder einer anderen funktionalen Programmiersprache haben, sind möglicherweise an verschiedene Idiome gewöhnt. In der folgenden Liste werden die empfohlenen F #-Operatoren zusammengefasst.

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Verwenden Sie Präfix Syntax für Generika ( `Foo<T>` ) in bevorzugter postfix Syntax ( `T Foo` ).

F # erbt sowohl den Postfix-ml-Stil der Benennung generischer Typen (z. b. `int list` ) als auch das Präfix .NET-Format (z `list<int>` . b.). Bevorzugen Sie den .net-Stil mit Ausnahme von fünf spezifischen Typen:

1. Verwenden Sie für F #-Listen das postfix-Formular: `int list` anstelle von `list<int>` .
2. Verwenden Sie für F #-Optionen das postfix-Formular: `int option` anstelle von `option<int>` .
3. Verwenden Sie für F #-Wert Optionen das postfix-Formular: `int voption` anstelle von `voption<int>` .
4. Verwenden Sie für F #-Arrays den syntaktischen Namen `int[]` anstelle von `int array` oder `array<int>` .
5. Verwenden Sie für Verweis Zellen `int ref` anstelle von `ref<int>` oder `Ref<int>` .

Verwenden Sie für alle anderen Typen das Präfix-Formular.

## <a name="formatting-tuples"></a>Formatierung von Tupeln

Eine tupelinstanziierung sollte in Klammern gesetzt werden, und auf die Trennzeichen in diesem muss ein einzelnes Leerzeichen folgen, z. b.: `(1, 2)` , `(x, y, z)` .

Es wird häufig angenommen, Klammern bei der Muster Übereinstimmung von Tupeln auszulassen:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

Es wird auch häufig angenommen, Klammern auszulassen, wenn das Tupel der Rückgabewert einer Funktion ist:

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

Zusammenfassend gilt, dass Tupel-Instanziierungen in Klammern bevorzugen, aber wenn Sie Tupel für den Musterabgleich oder einen Rückgabewert verwenden, wird es als ausreichend erachtet, Klammern zu vermeiden.

## <a name="formatting-discriminated-union-declarations"></a>Formatierung diskriminierter Union-Deklarationen

Einzug `|` in Typdefinition um vier Leerzeichen:

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

## <a name="formatting-discriminated-unions"></a>Formatieren diskriminierter Unions

Instanziierte Unterscheidungs-Unions, die auf mehrere Zeilen aufgeteilt werden, sollten enthaltene Daten einen neuen Bereich mit Einzug vermitteln:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

Die schließende Klammer kann sich auch in einer neuen Zeile befinden:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Formatieren von Datensätze

Einzug `{` in die Typdefinition um vier Leerzeichen, und die Feldliste wird in derselben Zeile gestartet:

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

Die Platzierung des öffnenden Tokens in einer neuen Zeile und das schließende Token in einer neuen Zeile ist vorzuziehen, wenn Sie Schnittstellen Implementierungen oder Member im Datensatz deklarieren:

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

## <a name="formatting-records"></a>Datensätze formatieren

Kurze Datensätze können in einer Zeile geschrieben werden:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Für Datensätze, die länger sind, sollten neue Zeilen für Bezeichnungen verwendet werden:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Wenn Sie das öffnende Token in einer neuen Zeile platzieren, wird der Inhalt in einem Bereich im Registerkarten Format angezeigt, und das schließende Token in einer neuen Zeile ist vorzuziehen, wenn Sie Folgendes ausführen:

* Verschieben von Datensätzen im Code mit unterschiedlichen Einzugs Bereichen
* Weiterleiten an eine Funktion

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

Die gleichen Regeln gelten für Listen-und Array Elemente.

## <a name="formatting-copy-and-update-record-expressions"></a>Formatieren von Ausdrücken zum Kopieren und Aktualisieren von Datensätzen

Ein Kopier-und Update Daten Satz Ausdruck ist immer noch ein Datensatz, daher gelten ähnliche Richtlinien.

Kurze Ausdrücke können in eine Zeile passen:

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

Längere Ausdrücke sollten neue Zeilen verwenden:

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = [ "Zippy"; "George"; "Bungle" ] }
```

Ebenso wie bei den Daten Satz Anleitungen sollten Sie separate Zeilen für geschweifte Klammern verwenden und einen Bereich mit dem Ausdruck nach rechts einziehen. In einigen besonderen Fällen (z. b. beim umschließen eines Werts mit einem optionalen ohne Klammern) müssen Sie möglicherweise eine geschweifter Klammer in einer Zeile aufbewahren:

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

Schreiben Sie `x :: l` mit Leerzeichen um den `::` Operator ( `::` ist ein Infix-Operator, der daher von Leerzeichen umgeben ist).

Listen und Arrays, die in einer einzelnen Zeile deklariert werden, müssen nach der öffnenden eckige Klammer und vor der schließenden Klammer ein Leerzeichen enthalten:

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen geschweifter Klammern ähnlichen Operatoren. Belassen Sie z. b. ein Leerzeichen zwischen einem `[` und einem `{` .

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

Listen und Arrays, die auf mehrere Zeilen aufgeteilt werden, folgen einer ähnlichen Regel wie Datensätze:

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

Ebenso wie bei Datensätzen wird durch das Deklarieren der öffnenden und schließenden Klammern in der eigenen Zeile das Verschieben von Code und das Weiterleiten in Funktionen vereinfacht.

Wenn Sie Arrays und Listen Programm gesteuert generieren, bevorzugen Sie, `->` `do ... yield` Wenn ein Wert immer generiert wird:

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

Ältere Versionen der F #-Sprache erforderten die Angabe von `yield` in Situationen, in denen Daten bedingt generiert werden können, oder es können aufeinanderfolgende Ausdrücke ausgewertet werden. Sie sollten diese Schlüsselwörter weglassen, `yield` es sei denn, Sie müssen mit einer älteren F #-Sprachversion kompilieren:

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

In einigen Fällen kann die Lesbarkeit von unter `do...yield` stützen. Diese Fälle, aber subjektiv, sollten berücksichtigt werden.

## <a name="formatting-if-expressions"></a>Formatieren von Ausdrücken

Der Einzug von Bedingungen hängt von der Größe und Komplexität der Ausdrücke ab, die Sie bilden.
Schreiben Sie diese einfach in eine Zeile, wenn:

- `cond`, `e1` und `e2` sind kurz
- `e1` und `e2` sind keine `if/then/else` Ausdrücke selbst.

```fsharp
if cond then e1 else e2
```

Wenn einer der Ausdrücke mehrzeilige oder Ausdrücke ist `if/then/else` .

```fsharp
if cond then
    e1
else
    e2
```

Mehrere Bedingungen mit `elif` und `else` werden im gleichen Gültigkeitsbereich wie das `if` eingerückt, wenn Sie den Regeln der einzeiligen `if/then/else` Ausdrücke folgen.

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

Wenn eine der Bedingungen oder Ausdrücke mehrzeilige Bedingungen hat, ist der gesamte `if/then/else` Ausdruck mehrzeilige Zeilen:

```fsharp
if cond1 then
    e1
elif cond2 then
    e2
elif cond3 then
    e3
else
    e4
```

### <a name="pattern-matching-constructs"></a>Musterabgleichkonstrukte

Verwenden Sie eine `|` for each-Klausel einer Entsprechung ohne Einzug. Wenn der Ausdruck kurz ist, können Sie die Verwendung einer einzelnen Zeile in Erwägung gezogen, wenn jeder Teil Ausdruck ebenfalls einfach ist.

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

Wenn der Ausdruck auf der rechten Seite des Musters für den Musterabgleich zu groß ist, verschieben Sie ihn in die folgende Zeile, wobei Sie einen Schritt aus der eingezogen haben `match` / `|` .

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Der Musterabgleich von anonymen Funktionen, beginnend mit `function` , sollte in der Regel nicht zu weit einziehen. Beispielsweise ist es in Ordnung, einen Bereich wie folgt einzuschließen:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Der Musterabgleich in Funktionen `let` , die von oder definiert `let rec` werden, sollte nach dem Start von vier Leerzeichen eingezogen werden `let` , auch wenn das- `function` Schlüsselwort verwendet wird

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Es wird nicht empfohlen, Pfeile auszurichten.

## <a name="formatting-trywith-expressions"></a>Formatieren von try/with-Ausdrücken

Der Musterabgleich für den Ausnahmetyp sollte auf der gleichen Ebene wie eingerückt werden `with` .

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

## <a name="formatting-function-parameter-application"></a>Formatieren der Funktionsparameter Anwendung

Im Allgemeinen werden die meisten Funktionsparameter Anwendungen in derselben Zeile ausgeführt.

Wenn Sie Parameter auf eine Funktion in einer neuen Zeile anwenden möchten, müssen Sie Sie um einen Bereich einziehen.

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

Die gleichen Richtlinien gelten auch für Lambda-Ausdrücke als Funktionsargumente. Wenn der Text eines Lambda Ausdrucks ist, kann der Text eine andere Zeile enthalten, die von einem Bereich eingezogen wird.

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

Wenn der Text eines Lambda-Ausdrucks jedoch mehr als eine Zeile ist, sollten Sie ihn in eine separate Funktion einbeziehen, anstatt ein mehr zeitiges Konstrukt als einzelnes Argument für eine Funktion anzuwenden.

### <a name="formatting-infix-operators"></a>Formatieren von Infixoperatoren

Getrennte Operatoren nach Leerzeichen. Offensichtliche Ausnahmen zu dieser Regel sind die `!` `.` Operatoren und.

Infix-Ausdrücke sind in der gleichen Spalte zu finden:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Formatierungs Pipeline Operatoren

Pipeline `|>` Operatoren sollten unterhalb der Ausdrücke liegen, die Sie verwenden.

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

Der Code in einem lokalen Modul muss relativ zum Modul eingezogen werden, aber der Code in einem Modul der obersten Ebene sollte nicht eingezogen werden. Namespace Elemente müssen nicht eingezogen werden.

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a * a + b * b

module A2 =
    let function2 a b = a * a - b * b
```

### <a name="formatting-object-expressions-and-interfaces"></a>Formatieren von Objekt Ausdrücken und Schnittstellen

Objekt Ausdrücke und Schnittstellen sollten auf die gleiche Weise ausgerichtet werden `member` , wenn Sie nach vier Leerzeichen eingezogen werden.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Formatieren von Leerzeichen in Ausdrücken

Vermeiden Sie überflüssige Leerzeichen in F #-Ausdrücken.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Benannte Argumente sollten auch keinen Platz enthalten, der das umgibt `=` :

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

### <a name="formatting-constructors-static-members-and-member-invocations"></a>Formatierungskonstruktoren, statische Member und Element Aufrufe

Wenn der Ausdruck kurz ist, trennen Sie Argumente mit Leerzeichen, und bewahren Sie Sie in einer Zeile auf.

```fsharp
let person = new Person(a1, a2)

let myRegexMatch = Regex.Match(input, regex)

let untypedRes = checker.ParseFile(file, source, opts)
```

Wenn der Ausdruck lang ist, verwenden Sie Zeilenumbrüche und einen Bereich, anstatt in die eckige Klammer einzuschließen.

```fsharp
let person =
    new Person(
        argument1,
        argument2
    )

let myRegexMatch =
    Regex.Match(
        "my longer input string with some interesting content in it",
        "myRegexPattern"
    )

let untypedRes =
    checker.ParseFile(
        fileName,
        sourceText,
        parsingOptionsWithDefines
    )
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

Sie sollten nach jeder XML-Dokumentation gehen:

```fsharp
/// Module with some things in it.
[<RequireQualifiedAccess>]
module M =
    let f x = x
```

### <a name="formatting-attributes-on-parameters"></a>Formatieren von Attributen für Parameter

Attribute können auch in Parameter eingefügt werden. Platzieren Sie in diesem Fall die Zeile in derselben Zeile wie der-Parameter und vor dem Namen:

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a>Formatieren mehrerer Attribute

Wenn mehrere Attribute auf ein Konstrukt angewendet werden, bei dem es sich nicht um einen Parameter handelt, sollten Sie so platziert werden, dass ein Attribut pro Zeile vorhanden ist:

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

Wenn Sie auf einen Parameter angewendet werden, müssen Sie sich in derselben Zeile befinden und durch ein Trennzeichen getrennt werden `;` .

## <a name="formatting-literals"></a>Formatieren von literalen

[F #-Literale](../language-reference/literals.md) , die das-Attribut verwenden, `Literal` sollten das-Attribut in einer eigenen Zeile platzieren und die Verwendung von PascalCase verwenden:

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

Vermeiden Sie das Platzieren des Attributs in derselben Zeile wie den Wert.

## <a name="formatting-computation-expression-operations"></a>Formatieren von Ausdrucks Operationen für Berechnungen

Beim Erstellen von benutzerdefinierten Vorgängen für [Berechnungs Ausdrücke](../language-reference/computation-expressions.md) empfiehlt es sich, die Namensgebung in CamelCase zu verwenden:

```fsharp
type MathBuilder () =
    member _.Yield _ = 0

    [<CustomOperation("addOne")>]
    member _.AddOne (state: int) =
        state + 1

    [<CustomOperation("subtractOne")>]
    member _.SubtractOne (state: int) =
        state - 1

    [<CustomOperation("divideBy")>]
    member _.DivideBy (state: int, divisor: int) =
        state / divisor

    [<CustomOperation("multiplyBy")>]
    member _.MultiplyBy (state: int, factor: int) =
        state * factor

let math = MathBuilder()

// 10
let myNumber =
    math {
        addOne
        addOne
        addOne

        subtractOne

        divideBy 2

        multiplyBy 10
    }
```

Die verwendete Benennungs Konvention sollte letztendlich von der zu modellierenden Domäne gesteuert werden.
Wenn es idiomatisch ist, eine andere Konvention zu verwenden, sollte diese Konvention stattdessen verwendet werden.
