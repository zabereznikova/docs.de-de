---
title: F#-Code Formatieren von Richtlinien
description: Erfahren Sie, Richtlinien zur Formatierung von F#-Code.
ms.date: 05/14/2018
ms.openlocfilehash: 0d7d2d1771710db55bf990f3a06079b2aec48fd7
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43858004"
---
# <a name="f-code-formatting-guidelines"></a>F#-Code Formatieren von Richtlinien

Dieser Artikel bietet Richtlinien zum Code zu formatieren, damit Ihre F#-Code ist:

* In der Regel als besser lesbar angezeigt.
* In Übereinstimmung mit Konventionen formatiert-Tools in Visual Studio und andere Editoren angewendet wird
* Ähnlich wie bei anderen Code online

Diese Leitlinien basieren auf [ein umfassendes Handbuch zum F#-Formatierungskonventionen](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) von [Anh-Dung Phan](https://github.com/dungpa).

## <a name="general-rules-for-indentation"></a>Allgemeine Regeln für den Einzug

F#-signifikanten Leerraum wird standardmäßig verwendet. Die folgenden Richtlinien dienen bieten eine Anleitung, wie einige Herausforderungen unter einen Hut bringen, die diese darstellen kann.

### <a name="using-spaces"></a>Mithilfe von Speicherplätzen

Wenn der Einzug erforderlich ist, müssen Sie Leerzeichen nicht Registerkarten verwenden. Mindestens ein Leerzeichen ist erforderlich. Ihre Organisation kann zum Angeben der Anzahl der Leerzeichen für Einzüge zu verwendende Codierungsstandards erstellen; zwei, drei oder vier Leerzeichen des Einzugs am jede Einzugsebene ist typisch.

**Es wird empfohlen, 4 Leerzeichen pro Einzug.**

Dies bedeutet, dass der Einzug der Programme eine subjektive Angelegenheit ist. Variationen sind in Ordnung, aber die erste Regel, die Sie befolgen sollten ist *Konsistenz des Einzugs*. Wählen Sie ein allgemein anerkannten Format des Einzugs und systematisch in Ihrer gesamten Codebasis verwenden.

## <a name="formatting-blank-lines"></a>Formatieren von Leerzeilen

* Separate auf oberster Ebene-Funktion und der Klassendefinition mit zwei Leerzeilen.
* Methodendefinitionen, die innerhalb einer Klasse werden durch eine einzelne leere Zeile getrennt.
* Zusätzliche Leerzeilen einfügen können (selten) verwendet werden, um Gruppen von verwandten Funktionen zu trennen. Leere Zeilen können zwischen einer Reihe von verwandten Einzeiler (z. B. ein Satz von platzhalterimplementierungen) weggelassen werden.
* Verwenden Sie Leerzeilen sparsam und nur dann in Funktionen, um logische Abschnitte anzugeben.

## <a name="formatting-comments"></a>Formatieren von Kommentaren

Ziehen Sie in der Regel mehrere Kommentaren mit doppelten Schrägstrichen blockskommentaren ML-Format vor.

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

Inlinekommentare sollte der erste Buchstabe groß geschrieben.

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a>Namenskonventionen 

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a>Verwenden Sie CamelCase für die Klasse, ausdrucksgebundenen als auch Muster – gebunden Werte und Funktionen

Es ist üblich und akzeptierte F#-Stil verwenden Sie CamelCase für alle Namen gebunden, als lokale Variablen oder in musterübereinstimmungen und Funktionsdefinitionen.

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

Lokale gebundene Funktionen in Klassen sollten auch CamelCase verwenden.

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a>Verwenden Sie CamelCase für Öffentliche Modul-Bound-Funktionen

Wenn eine Modul-Bound-Funktion eine öffentliche API gehört, sollten sie CamelCase verwenden:

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a>Verwenden Sie CamelCase für interne und private Modul-Bound-Werte und Funktionen

Verwenden Sie CamelCase für private Modul-Bound-Werte, einschließlich der folgenden:

* Ad-hoc-Funktionen in Skripts

* Werte, aus denen die interne Implementierung der ein Modul oder Typ

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a>Verwenden Sie CamelCase für Parameter

Alle Parameter sollten CamelCase gemäß den Konventionen zur Namensgebung von .NET verwenden.

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a>Verwenden Sie PascalCase für Module.

Alle Module (der obersten Ebene, interne, private, geschachtelte) sollten PascalCase verwenden.

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a>Verwenden von PascalCase für Deklarationen von Typen, Member und Bezeichnungen

Klassen, Schnittstellen, Strukturen, Enumerationen, Delegaten, Datensätze und Unterscheidungs-Unions sollten alle mit PascalCase benannt werden. Außerdem sollten die Elemente innerhalb der Typen und Bezeichnungen für Datensätze und Unterscheidungs-Unions PascalCase verwenden.

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a>Verwendung von PascalCase für Konstrukte auf .NET systeminterne

Namespaces, Ausnahmen, Ereignisse und Projekt /`.dll` Namen sollten auch PascalCase verwenden. Nicht nur macht dies Verbrauch von anderen .NET-Sprachen können Sie erwarten, dass Kunden, es ist auch mit .NET Benennungskonventionen, die Sie wahrscheinlich konfrontiert sind konsistent.

### <a name="avoid-underscores-in-names"></a>Vermeiden Sie die Unterstriche im Namen

In der Vergangenheit haben einige F#-Bibliotheken Unterstriche im Namen verwendet. Allerdings wird dies häufig nicht mehr akzeptiert, teilweise daran, dass sie mit .NET Benennungskonventionen verursacht einen Konflikt. Allerdings einige F#-Programmierer verwenden Unterstriche stark, teilweise historisch bedingt und Fehlertoleranz und Respekt ist wichtig. Bedenken Sie jedoch, dass der Stil häufig von anderen gefällt mir nicht ist, die eine Wahl darüber, ob sie verwendet haben.

Einige Ausnahmen umfasst die Interaktion mit nativen Komponenten, in denen Unterstriche sind sehr häufig.

### <a name="use-standard-f-operators"></a>Verwenden Sie die standardmäßige F#-Operatoren

Die folgenden Operatoren werden in der F#-Standardbibliothek definiert und sollte verwendet werden, anstatt Entsprechungen. Mit diesen Operatoren wird empfohlen, wie sie Code besser lesbar und idiomatische machen ist. Entwickler mit einem Hintergrund mit OCaml oder andere funktionale Programmiersprache ggf. daran gewöhnt, Idiome zu sein. Die folgende Liste enthält die empfohlenen F#-Operatoren.

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a>Verwenden Sie Generika Präfix-Syntax (`Foo<T>`) statt Postfix-Syntax (`T Foo`)

F#-erbt sowohl den Postfix ML Stil für die Benennung von generischer Typen (z. B. `int list`) sowie das Präfix .NET Stil (z. B. `list<int>`). Bevorzugen Sie das .NET-Format, mit Ausnahme von vier bestimmte Typen:

1. Für f#-Listen, verwenden Sie die Postfix-Form: `int list` statt `list<int>`.
2. Für die F#-Optionen verwenden Sie die Postfix-Form: `int option` statt `option<int>`.
3. Verwenden Sie für F#-Arrays, die syntaktischen Namen `int[]` statt `int array` oder `array<int>`.
4. Verwenden Sie für Referenzzellen, `int ref` statt `ref<int>` oder `Ref<int>`.

Verwenden Sie für alle anderen Dateitypen die Präfix-Form.

## <a name="formatting-tuples"></a>Formatieren von Tupeln

Eine Instanziierung Tupel muss in Klammern ein, und die begrenzenden Kommas innerhalb von sollte z. B. durch ein Leerzeichen, gefolgt werden: `(1, 2)`, `(x, y, z)`.

Es wird häufig zum Auslassen von Klammern in Musterabgleich von Tupeln akzeptiert:

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

## <a name="formatting-discriminated-union-declarations"></a>Formatieren von Unterscheidungs-union-Deklarationen

Einzug `|` in der Definition des Typs von 4 Leerzeichen:

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

## <a name="formatting-discriminated-unions"></a>Formatieren von Unterscheidungs-unions

Instanziierte Unterscheidungs-Unions, die über mehrere Zeilen aufgeteilt sollte enthaltenen Daten einen neuen Bereich mit Einzug bieten:

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

Die schließende Klammer kann auch in einer neuen Zeile werden:

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a>Formatieren von Datensatz-Deklarationen

Einzug `{` Geben Sie in die Definition von 4 Leerzeichen und die Feldliste in der gleichen Zeile beginnen:

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

Das öffnendes-Token auf der gleichen Zeile und dem schließenden-Token in einer neuen Zeile platziert ist ebenfalls in Ordnung, aber beachten Sie, dass Sie benötigen die [ausführliche Syntax](../language-reference/verbose-syntax.md) um Elemente zu definieren (die `with` Schlüsselwort):

```fsharp
//  OK, but verbose syntax required
type PostalAddress = { 
    Address: string
    City: string
    Zip: string
} with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City
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

Es ist auch in Ordnung, das öffnendes-Token auf der gleichen Zeile und dem schließenden-Token in einer neuen Zeile platziert:

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

Die gleichen Regeln gelten für Listen- und Elemente.

## <a name="formatting-lists-and-arrays"></a>Formatieren von Listen und arrays

Schreiben von `x :: l` mit Leerzeichen vor und hinter der `::` Operator (`::` ist ein Infix-Operator, daher Leerzeichen enthaltender) und `[1; 2; 3]` (`;` ein Trennzeichen, daher gefolgt von einem Leerzeichen).

Verwenden Sie immer mindestens ein Leerzeichen zwischen zwei unterschiedlichen geschweifte Klammer-Like-Operatoren. Lassen Sie beispielsweise einem Leerzeichen zwischen einem `[` und `{`.

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

Listen und Arrays, die über mehrere Zeilen aufgeteilt. Führen Sie eine ähnliche Regel, wie Datensätze:

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

## <a name="formatting-if-expressions"></a>Formatierung-If-Ausdrücke

Einzug von Bedingungen hängt von der Größe der Ausdrücke, die sie sich machen ab. Wenn `cond`, `e1` und `e2` sind kurze, Schreiben Sie sie einfach auf eine Zeile:

```fsharp
if cond then e1 else e2
```

Wenn entweder `cond`, `e1` oder `e2` sind länger, aber nicht mit mehreren Zeilen:

```fsharp
if cond
then e1
else e2
```

Wenn einer der Ausdrücke mit mehreren Zeilen sind:

```fsharp
if cond then
    e1
else
    e2
```

Mehrere Bedingungen mit `elif` und `else` werden eingerückt unter dem gleichen Bereich wie die `if`:

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a>Übereinstimmende Muster-Konstrukte

Verwenden einer `|` für jede Klausel einer Übereinstimmung mit ohne Einzug. Wenn der Ausdruck kurz ist, können Sie erwägen, eine einzelne Zeile verwenden, wenn jede Teilausdruck auch einfach ist.

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
```

Wenn der Ausdruck auf der rechten Seite der Musterabgleich Pfeil zu groß ist, verschieben Sie sie auf der folgenden Zeile eingezogen einen Schritt aus dem `match` / `|`.

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

Mustervergleich von anonymen Funktionen, die gestartet wird, indem `function`, sollte im Allgemeinen nicht einrücken zu weit. Beispielsweise reicht Einzug einen Bereich wie folgt:

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

Mustervergleiche in Funktionen, die von definiert `let` oder `let rec` muss eingezogene 4 Leerzeichen nach dem Starten des `let`, auch wenn `function` -Schlüsselwort wird verwendet:

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

Wir empfehlen nicht, Pfeile ausrichten.

## <a name="formatting-trywith-expressions"></a>Formatierung Try / with-Ausdrücke

Musterabgleich für den Typ der Ausnahme sollte eingezogen werden, auf der gleichen Ebene wie `with`.

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

Die meisten funktionsanwendung-Parameter wird in der Regel in der gleichen Zeile durchgeführt.

Wenn Sie, um Parameter an eine Funktion in einer neuen Zeile anzuwenden möchten, Rücken Sie diese durch einen Bereich.

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

Die gleichen Richtlinien gelten für Lambda-Ausdrücke als Argumente der Funktion. Wenn der Text eines Lambda-Ausdrucks, der Text einer anderen Zeile eingerückt wird, indem Sie einen Bereich enthalten kann

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

Allerdings ist der Text eines Lambdaausdrucks mehrere Zeilen, sollten Sie ihn in eine separate Funktion Finanzierung anstelle einer mehrzeiligen-Konstrukt, das als einzelnes Argument an eine Funktion angewendet.

### <a name="formatting-infix-operators"></a>Formatieren von Infixoperatoren

Separate Operatoren durch Leerzeichen. Offensichtliche Ausnahmen von dieser Regel werden die `!` und `.` Operatoren.

Infix-Ausdrücke sind in Ordnung LineUp auf dieselbe Spalte:

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a>Formatieren von Pipeline-Operatoren

Pipeline `|>` Operatoren gesendet werden sollen, darunter die Ausdrücke, die sie verarbeiten.

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

Code in einem lokalen Modul muss sich auf das Modul eingezogen werden, jedoch Code in einem Modul auf oberster Ebene sollten nicht eingerückt werden. Namespace-Elemente müssen nicht mit Einzug dargestellt werden.

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

### <a name="formatting-object-expressions-and-interfaces"></a>Formatieren von Object-Ausdrücke und Schnittstellen

Object-Ausdrücke und Schnittstellen sollten auf die gleiche Weise mit ausgerichtet werden `member` nach 4 Leerzeichen eingerückt wird.

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s : String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a>Formatieren von Leerzeichen in Ausdrücken

Vermeiden Sie die überflüssigen Leerzeichen in f#-Ausdrücke.

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

Benannte Argumente dürfen auch keine Leerzeichen, umgibt die `=`:

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```
