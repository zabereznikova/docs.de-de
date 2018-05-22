---
title: F#-Code, die Formatierung von Richtlinien
description: Erfahren Sie Richtlinien zur Formatierung von F#-Code ein.
ms.date: 05/14/2018
ms.openlocfilehash: 1433b6891a6a0ddcdc082c141365ae54fa40c27b
ms.sourcegitcommit: 22c3c8f74eaa138dbbbb02eb7d720fce87fc30a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="f-code-formatting-guidelines"></a>F#-Code, die Formatierung von Richtlinien

Dieser Artikel bietet Richtlinien zum Code formatieren, sodass der f#-Code ist:

* Im Allgemeinen als besser lesbar angezeigt.
* In Übereinstimmung mit den Konventionen, die durch die Tools in Visual Studio und andere Editoren Formatierung angewendet wird
* Ähnlich wie bei anderen Code online

Diese Richtlinien basieren auf [eine umfassende Anleitung zum F#-Formatierung Konventionen](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) von [Anh Mist Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Allgemeine Regeln für den Einzug

F#-signifikanten Leerräume wird standardmäßig verwendet. Die folgenden Richtlinien sollen bieten eine Anleitung, wie einige Herausforderungen Grenzen gesetzt sind, die kann dies zu erzwingen.

### <a name="using-spaces"></a>Durch Leerzeichen getrennt werden

Wenn Einzug erforderlich ist, müssen Sie Leerzeichen, nicht-Registerkarten verwenden. Mindestens eine Leerstelle ist erforderlich. Ihre Organisation kann Codierungsstandards zum Angeben der Anzahl von Leerzeichen zum einrücken verwendet erstellen; zwei, drei oder vier Speicherplätzen Einzugsebene an jede Einzugsebene entspricht den Erwartungen.

**Es wird empfohlen, 4 Leerzeichen pro Einzug.**

Dies bedeutet, dass der Einzug der Programme eine subjektive Angelegenheit ist. Varianten sind in Ordnung, jedoch ist die erste Regel, die Sie befolgen sollten *Konsistenz des Einzugs*. Wählen Sie ein allgemein anerkannten Format des Einzugs und systematisch in der gesamten Codebasis verwenden.

## <a name="formatting-discriminated-union-declarations"></a>Formatieren von Unterscheidungs-union-Deklarationen

Ziehen Sie ein `|` in Typdefinition durch 4 Leerzeichen:

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

Instanziierte Unterscheidungs-Unions, die auf mehrere Zeilen aufgeteilt sollte enthaltenen Daten einen neuen Bereich mit Einzügen vermitteln:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

Die schließende Klammer in einer neuen Zeile ist auch möglich:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-tuples"></a>Formatieren von Tupeln

Eine Instanziierung der Tupel in Klammern werden sollte und der begrenzenden Kommas innerhalb sollte darauf folgen durch ein Leerzeichen, z. B.: `(1, 2)`, `(x, y, z)`.

Eine häufig akzeptierte Ausnahme besteht darin, Klammern in einem Mustervergleich von Tupeln auszuschließen:

```fsharp
let (x, y) = z // Destructuring

match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-records"></a>Formatieren von Datensätzen

Kurze Datensätze können in einer Zeile geschrieben werden:

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

Datensätze, die länger sind, sollten neue Zeilen für Bezeichnungen verwenden:

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

Das öffnende-Token auf der gleichen Zeile und das schließende-Token in einer neuen Zeile platziert wird auch keine Probleme:

```fsharp
let rainbow = {
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
```

Es gelten die gleichen Regeln für Liste und Array-Elemente.

## <a name="formatting-lists-and-arrays"></a>Formatieren von Listen und arrays

Schreiben von `x :: l` mit Leerzeichen der `::` Operator (`::` ist ein Infix-Operator, daher Leerzeichen enthaltender) und `[1; 2; 3]` (`;` ist ein Trennzeichen, daher gefolgt von einem Leerzeichen).

Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen geschweifte Klammer-ähnliche Operatoren ein. Lassen Sie z. B. ein Leerzeichen zwischen einem `[` und ein `{`.

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

Listen und Arrays, die auf mehrere Zeilen aufgeteilt führen Sie eine ähnliche Regel, wie Datensätze:

```fsharp
let pascalsTriangle = [|
    [|1|]
    [|1; 1|]
    [|1; 2; 1|]
    [|1; 3; 3; 1|]
    [|1; 4; 6; 4; 1|]
    [|1; 5; 10; 10; 5; 1|]
    [|1; 6; 15; 20; 15; 6; 1|]
    [|1; 7; 21; 35; 35; 21; 7; 1|]
    [|1; 8; 28; 56; 70; 56; 28; 8; 1|]
|]
```

## <a name="formatting-if-expressions"></a>Formatierung If Ausdrücke

Einzug des Konditionelle Abschnitte hängt die Größen von Ausdrücken, die sie bilden. Wenn `cond`, `e1` und `e2` "klein", werden sie einfach auf eine Zeile zu schreiben:

```fsharp
if cond then e1 else e2
```

Wenn `e1` und `cond` "klein", sind aber `e2` groß ist:

```fsharp
if cond then e1
else
    e2
```

Wenn `e1` und `cond` Groß und `e2` ist klein:

```fsharp
if cond then
    e1
else e2
```

Wenn alle Ausdrücke groß sind:

```fsharp
if cond then
    e1
else
    e2
```

Mehrere Bedingungen mit `elif` und `else` eingezogen im gleichen Bereich wie die `if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Übereinstimmende Muster-Konstrukte

Verwenden einer `|` für jede Klausel einer Übereinstimmung ohne Einzug. Wenn der Ausdruck kurz ist, können Sie eine einzelne Zeile verwenden.

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> _
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> _
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"

// OK
match l with [] -> false | _ :: _ -> true
```

Wenn der Ausdruck auf der rechten Seite der Musterabgleich Pfeil zu groß ist, verschieben Sie sie auf der folgenden Zeile eingezogen einen Schritt aus der `match` / `|`.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Anonyme Funktionen, die gestartet wird, indem den Mustervergleich `function`, sollte im Allgemeinen nicht Einzug zu weit. Beispielsweise ist das Festlegen von Einzügen für einen Bereich wie folgt Ordnung:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Mustervergleich in Funktionen, die definiert, indem `let` oder `let rec` muss eingezogene 4 Leerzeichen nach dem Starten der `let`, selbst wenn `function` -Schlüsselwort wird verwendet:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Wir empfehlen nicht Pfeile ausrichten.

## <a name="formatting-trywith-expressions"></a>Formatierung Try / mit-Ausdrücken

Einen Mustervergleich für den Ausnahmetyp sollte auf der gleichen Ebene wie eingezogen werden `with`.

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

## <a name="formatting-function-parameter-application"></a>Formatieren von funktionsanwendung-parameter

Im Allgemeinen erfolgt die meisten funktionsanwendung Parameter in derselben Zeile.

Wenn Sie Parameter an eine Funktion in einer neuen Zeile anwenden möchten, Rücken Sie diese durch einen Bereich.

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

Anonyme Funktionsargumente können sein, auf die nächste Zeile oder mit einem Verbleibend `fun` in der Argumentzeile:

```fsharp
// OK
let printListWithOffset a list1 =
    List.iter (fun elem ->
        printfn "%d" (a + elem)) list1

// OK, but prefer previous
let printListWithOffset a list1 =
    List.iter (
        fun elem ->
            printfn "%d" (a + elem)) list1
```

### <a name="formatting-infix-operators"></a>Formatieren von Infixoperatoren

Separate Operatoren durch Leerzeichen. Offensichtliche Ausnahmen von dieser Regel werden die `!` und `.` Operatoren.

Infix-Ausdrücke sind in Ordnung LineUp für dieselbe Spalte:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Formatieren von Pipeline-Operatoren

Pipeline `|>` Operatoren verwendende unterhalb der Ausdrücke, die sie verarbeiten.

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

Code in einem lokalen Modul muss relativ zum Modul eingezogen werden, jedoch Code in einem Modul der obersten Ebene nicht eingezogen werden soll. Namespace-Elemente müssen nicht mit Einzug dargestellt werden.

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

### <a name="formatting-object-expressions-and-interfaces"></a>Formatieren von Objektausdrücke und Schnittstellen

Objektausdrücke und Schnittstellen auf die gleiche Weise mit ausgerichtet sein `member` wird nach 4 Leerzeichen eingezogen.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-whitespace-in-expressions"></a>Formatieren von Leerzeichen in Ausdrücken

Vermeiden Sie unnötige Leerstellen in f#-Ausdrücke.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Benannte Argumente sollten auch keinen Speicherplatz umgebenden der `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-blank-lines"></a>Formatieren von Leerzeilen

* Separate auf oberster Ebene Funktion und der Klassendefinition mit zwei leere Zeilen.
* Methodendefinitionen innerhalb einer Klasse werden durch eine einzelne Leerzeile getrennt.
* Zusätzliche leere Zeilen können (nur selten) in separate Gruppen verwandter Funktionen verwendet werden. Leerzeilen können zwischen einer Reihe von verwandten Einzeiler (z. B. ein Satz von dummy-Implementierungen) ausgelassen werden.
* Verwenden Sie leere Zeilen nur selten, in Funktionen, um logische Abschnitte anzugeben.

## <a name="formatting-comments"></a>Formatieren von Kommentaren

Ziehen Sie in der Regel mehrere doppelten Schrägstrich Kommentare ML-Stil Blocks-Kommentaren.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    Generally avoid these kinds of comments.
*)
```

Inline-Kommentare, sollte der erste Buchstabe groß geschrieben.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Namenskonventionen 

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Verwenden Sie camelCase ändern möchten, für gebundene Klasse, Ausdruck auch Muster gebunden Werte und Funktionen

Es kommt häufig vor und akzeptierte F#-Format, das camelCase ändern möchten nach allen Namen gebunden, als lokale Variablen oder Muster Matches "und" Funktionsdefinitionen.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Lokalen gebundenen Funktionen in Klassen verwenden zudem camelCase ändern möchten.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Verwenden Sie camelCase ändern möchten, für die interne und private Modul gebundenen Werte und Funktionen

Verwenden Sie camelCase ändern möchten, für die private Modul gebundenen Werte, einschließlich der folgenden:

* Ad-hoc-Funktionen in Skripts

* Werte, aus denen die interne Implementierung der ein Modul oder einen Typ

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Verwenden Sie camelCase ändern möchten, für Parameter

Alle Parameter sollten camelCase ändern möchten, in Übereinstimmung mit den Konventionen zur Namensgebung von .NET verwenden.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Verwenden Sie "PascalCase" für Module

Alle Module (auf der obersten Ebene, interne, private, geschachtelte) sollten "PascalCase" verwenden.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Verwenden Sie "PascalCase" für Deklarationen von Typen, Member und Beschriftungen

Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und Unterscheidungs-Unions sollten alle mit "PascalCase" benannt werden. Außerdem sollten die Elemente innerhalb der Typen und Bezeichnungen für Datensätze und Unterscheidungs-Unions "PascalCase" verwenden.

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Verwenden Sie "PascalCase" Konstrukte für .NET

Namespaces, Ausnahmen, Ereignisse und Projekt /`.dll` Namen sollte auch "PascalCase" verwenden. Nicht nur dadurch, Verbrauch aus anderen .NET-Sprachen natürlicher für Consumer können, ist auch konsistent mit dem .NET Benennungskonventionen, die Sie stoßen können.

### <a name="avoid-underscores-in-names"></a>Vermeiden Sie Unterstriche im Namen

In der Vergangenheit haben einige f#-Bibliotheken Unterstriche im Namen verwendet. Allerdings wird dies häufig nicht mehr akzeptiert, da mit den Benennungskonventionen für .NET Konflikt. Dies bedeutet, dass einige f#-Programmierer verwenden Sie Unterstriche stark, teilweise aus Verlaufsgründen und Fehlertoleranz zu gewährleisten und Hinsicht ist wichtig. Denken Sie jedoch, dass die Formatvorlage häufig von anderen disliked ist, die Wahl, ob Sie, ob es verwendet haben.

Einige Ausnahmen enthält Interoperabilität mit systemeigenen Komponenten, in denen Unterstriche üblich sind.

### <a name="use-standard-f-operators"></a>Verwenden Sie die standard-Operatoren [F#]

Die folgenden Operatoren werden in der f#-Standardbibliothek definiert und sollte verwendet werden, statt zu Entsprechungen definieren. Mithilfe dieser Operatoren wird empfohlen, wie sie Code besser lesbar und idiomatische ist ist. Entwickler mit einem Hintergrund mit OCaml oder anderen funktionalen Programmierung Sprache möglicherweise mit anderen Idiome vertraut sein. Die folgende Liste fasst die empfohlene F#-Operatoren.

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Throwing away a value
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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Verwenden Sie die Präfix-Syntax für Generika (`Foo<T>`) aufrufanweisung Postfix-Syntax (`T Foo`)

F#-erbt sowohl den Postfix ML Stil für die Benennung von generischer Typen (z. B. `int list`) sowie das Präfix .NET Stil (z. B. `list<int>`). Bevorzugen Sie .NET Formatvorlage, mit Ausnahme von vier bestimmte Typen:

1. Verwenden Sie für f#-Listen, die Postfix-Form: `int list` statt `list<int>`.
2. Verwenden Sie für f#-Optionen, die Postfix-Form: `int option` statt `option<int>`.
3. Verwenden Sie für f#-Arrays, die syntaktischen Namen `int[]` statt `int array` oder `array<int>`.
4. Verwenden Sie Referenzzellen, `int ref` statt `ref<int>` oder `Ref<int>`.

Verwenden Sie für alle anderen Datentypen die Präfix-Form.
