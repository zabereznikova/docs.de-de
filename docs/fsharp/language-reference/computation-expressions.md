---
title: Berechnungsausdrücke
description: Erfahren Sie, wie Sie praktische Syntax zum Schreiben von Berechnungen in F- erstellen, die mithilfe von Steuerungsflusskonstrukten und -bindungen sequenziert und kombiniert werden können.
ms.date: 11/04/2019
ms.openlocfilehash: 55406cc12d9e6e890fe69d712f79486d23b84452
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401082"
---
# <a name="computation-expressions"></a>Berechnungsausdrücke

Berechnungsausdrücke in F' bieten eine praktische Syntax zum Schreiben von Berechnungen, die mithilfe von Steuerungsflusskonstrukten und -bindungen sequenziert und kombiniert werden können. Je nach Art des Berechnungsausdrucks können sie als eine Möglichkeit betrachtet werden, Monaden, Monoide, Monadentransformatoren und applikative Funker auszudrücken. Im Gegensatz zu anderen Sprachen (z. B. *Do-Notation* in Haskell) sind sie jedoch nicht an eine einzelne Abstraktion gebunden und verlassen sich nicht auf Makros oder andere Formen der Metaprogrammierung, um eine bequeme und kontextsensitive Syntax zu erreichen.

## <a name="overview"></a>Übersicht

Berechnungen können viele Formen annehmen. Die häufigste Form der Berechnung ist die Ausführung mit einem Thread, die leicht zu verstehen und zu ändern ist. Allerdings sind nicht alle Formen der Berechnung so einfach wie die Ausführung mit einem Thread. Beispiele hierfür sind:

- Nicht deterministische Berechnungen
- Asynchrone Berechnungen
- Effektive Berechnungen
- Generative Berechnungen

Im Allgemeinen gibt es *kontextsensitive* Berechnungen, die Sie in bestimmten Teilen einer Anwendung durchführen müssen. Das Schreiben von kontextsensitivem Code kann eine Herausforderung sein, da es einfach ist, Berechnungen außerhalb eines bestimmten Kontexts ohne Abstraktionen zu "lecken", um Sie daran zu hindern. Diese Abstraktionen sind oft eine Herausforderung, um selbst zu schreiben, weshalb f. eine verallgemeinerte Möglichkeit hat, so genannte **Berechnungsausdrücke**zu tun.

Berechnungsausdrücke bieten ein einheitliches Syntax- und Abstraktionsmodell für die Codierung kontextsensitiver Berechnungen.

Jeder Berechnungsausdruck wird von einem *Buildertyp* unterstützt. Der Buildertyp definiert die Vorgänge, die für den Berechnungsausdruck verfügbar sind. Weitere Informationen finden Sie unter [Erstellen eines neuen Berechnungsausdrucks](computation-expressions.md#creating-a-new-type-of-computation-expression), der zeigt, wie ein benutzerdefinierter Berechnungsausdruck erstellt wird.

### <a name="syntax-overview"></a>Syntaxübersicht

Alle Berechnungsausdrücke haben die folgende Form:

```fsharp
builder-expr { cexper }
```

Wobei `builder-expr` der Name eines Builder-Typs ist, `cexper` der den Berechnungsausdruck definiert, und der Ausdruckskörper des Berechnungsausdrucks ist. Der Berechnungsexpressionscode `async` kann z. B. wie folgt aussehen:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

In einem Berechnungsausdruck ist eine spezielle, zusätzliche Syntax verfügbar, wie im vorherigen Beispiel gezeigt. Die folgenden Ausdrucksformen sind mit Berechnungsausdrücken möglich:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Jedes dieser Schlüsselwörter und andere Standardschlüsselwörter sind nur in einem Berechnungsausdruck verfügbar, wenn sie im Sicherungs-Generatortyp definiert wurden. Die einzige Ausnahme `match!`ist , die selbst syntaktischer `let!` Zucker für die Verwendung von gefolgt von einem Muster Übereinstimmung auf das Ergebnis ist.

Der Builder-Typ ist ein Objekt, das spezielle Methoden definiert, die die Art und Weise steuern, wie die Fragmente des Berechnungsausdrucks kombiniert werden. Das heißt, seine Methoden steuern, wie sich der Berechnungsausdruck verhält. Eine andere Möglichkeit, eine Builder-Klasse zu beschreiben, besteht darin, zu sagen, dass Sie damit die Operation vieler F-Konstrukte anpassen können, z. B. Schleifen und Bindungen.

### `let!`

Das `let!` Schlüsselwort bindet das Ergebnis eines Aufrufs an einen anderen Berechnungsausdruck an einen Namen:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Wenn Sie den Aufruf an `let`einen Berechnungsausdruck mit binden, erhalten Sie nicht das Ergebnis des Berechnungsausdrucks. Stattdessen haben Sie den Wert des *nicht realisierten* Aufrufs an diesen Berechnungsausdruck gebunden. Verwenden `let!` Sie diese Datei, um an das Ergebnis zu binden.

`let!`wird durch `Bind(x, f)` das Element im Buildertyp definiert.

### `do!`

Das `do!` Schlüsselwort dient zum Aufrufen `unit`eines Berechnungsausdrucks, `Zero` der einen -like-Typ zurückgibt (definiert durch den Member auf dem Builder):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

Für den [async-Workflow](asynchronous-workflows.md) `Async<unit>`lautet dieser Typ . Bei anderen Berechnungsausdrücken ist `CExpType<unit>`der Typ wahrscheinlich .

`do!`wird durch `Bind(x, f)` das Element auf dem `f` Builder-Typ definiert, wobei eine erzeugt wird. `unit`

### `yield`

Das `yield` Schlüsselwort dient zum Zurückgeben eines Werts aus dem <xref:System.Collections.Generic.IEnumerable%601>Berechnungsausdruck, damit er als :

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

In den meisten Fällen kann es von Aufrufern weggelassen werden. Der häufigste Weg, `yield` um zu `->` unterlassen ist mit dem Operator:

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

Bei komplexeren Ausdrücken, die viele verschiedene Werte ergeben können, und möglicherweise bedingt, kann das Auslassen des Schlüsselworts:

```fsharp
let weekdays includeWeekend =
    seq {
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    }
```

Wie beim [yield-Schlüsselwort in C-](../../csharp/language-reference/keywords/yield.md)wird jedes Element im Berechnungsausdruck zurückgegeben, wenn es iteriert wird.

`yield`wird durch `Yield(x)` das Element im Builder-Typ definiert, wobei `x` das Element zurückgegeben werden soll.

### `yield!`

Das `yield!` Schlüsselwort dient zum Abflachen einer Auflistung von Werten aus einem Berechnungsausdruck:

```fsharp
let squares =
    seq {
        for i in 1..3 -> i * i
    }

let cubes =
    seq {
        for i in 1..3 -> i * i * i
    }

let squaresAndCubes =
    seq {
        yield! squares
        yield! cubes
    }

printfn "%A" squaresAndCubes // Prints - 1; 4; 9; 1; 8; 27
```

Bei der Auswertung wird `yield!` der von aufgerufene Berechnungsausdruck seine Elemente nacheinander zurückgeben und das Ergebnis verflachen.

`yield!`wird durch `YieldFrom(x)` den Member im Buildertyp definiert, wobei es sich `x` um eine Auflistung von Werten handelt.

Im `yield` `yield!` Gegensatz zu muss explizit angegeben werden. Sein Verhalten ist in Berechnungsausdrücken nicht implizit.

### `return`

Das `return` Schlüsselwort umschließt einen Wert in dem Typ, der dem Berechnungsausdruck entspricht. Abgesehen von Berechnungsausdrücken, `yield`die verwendet werden, wird es verwendet, um einen Berechnungsausdruck zu "vervollständigen":

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return`wird durch `Return(x)` das Element im Buildertyp definiert, wobei `x` das zu umschließende Element ist.

### `return!`

Das `return!` Schlüsselwort erkennt den Wert eines Berechnungsausdrucks und umschließt den Typ, der dem Berechnungsausdruck entspricht:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!`wird durch `ReturnFrom(x)` das Element im Buildertyp definiert, wobei `x` es sich um einen anderen Berechnungsausdruck handelt.

### `match!`

Mit `match!` dem Schlüsselwort können Sie einen Aufruf eines anderen Berechnungsausdrucks und einer Musterübereinstimmung für das Ergebnis inline:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

Beim Aufrufen eines `match!`Berechnungsausdrucks mit wird das `let!`Ergebnis des Aufrufs wie realisiert. Dies wird häufig beim Aufrufen eines Berechnungsausdrucks verwendet, bei dem das Ergebnis ein [optionaler](options.md)ist.

## <a name="built-in-computation-expressions"></a>Integrierte Berechnungsausdrücke

Die Kernbibliothek von F- definiert drei integrierte Berechnungsausdrücke: [Sequenzausdrücke](sequences.md), [Asynchrone Workflows](asynchronous-workflows.md)und [Abfrageausdrücke](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Erstellen eines neuen Berechnungsausdruckstyps

Sie können die Merkmale Ihrer eigenen Berechnungsausdrücke definieren, indem Sie eine Builder-Klasse erstellen und bestimmte spezielle Methoden für die Klasse definieren. Die Builder-Klasse kann optional die in der folgenden Tabelle aufgeführten Methoden definieren.

In der folgenden Tabelle werden Methoden beschrieben, die in einer Workflow-Builderklasse verwendet werden können.

|**Methode**|**Typische Signatur(n)**|**Beschreibung**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Aufgerufen `let!` für `do!` und in Berechnungsausdrücken.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Umschließt einen Berechnungsausdruck als Funktion.|
|`Return`|`'T -> M<'T>`|In `return` Berechnungsausdrücken aufgerufen.|
|`ReturnFrom`|`M<'T> -> M<'T>`|In `return!` Berechnungsausdrücken aufgerufen.|
|`Run`|`M<'T> -> M<'T>` oder<br /><br />`M<'T> -> 'T`|Führt einen Berechnungsausdruck aus.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` oder<br /><br />`M<unit> * M<'T> -> M<'T>`|Wird zur Sequenzierung in Berechnungsausdrücken aufgerufen.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` oder<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Wird `for...do` für Ausdrücke in Berechnungsausdrücken aufgerufen.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Wird `try...finally` für Ausdrücke in Berechnungsausdrücken aufgerufen.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Wird `try...with` für Ausdrücke in Berechnungsausdrücken aufgerufen.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|Wird `use` für Bindungen in Berechnungsausdrücken aufgerufen.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Wird `while...do` für Ausdrücke in Berechnungsausdrücken aufgerufen.|
|`Yield`|`'T -> M<'T>`|Wird `yield` für Ausdrücke in Berechnungsausdrücken aufgerufen.|
|`YieldFrom`|`M<'T> -> M<'T>`|Wird `yield!` für Ausdrücke in Berechnungsausdrücken aufgerufen.|
|`Zero`|`unit -> M<'T>`|Wird für `else` leere `if...then` Auszweigungen von Ausdrücken in Berechnungsausdrücken aufgerufen.|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|Gibt an, dass der `Run` Berechnungsausdruck als Zitat an das Element übergeben wird. Es übersetzt alle Instanzen einer Berechnung in ein Zitat.|

Viele der Methoden in einer Builderklasse `M<'T>` verwenden und geben ein Konstrukt zurück, bei dem es sich in `Async<'T>` der Regel um `Seq<'T>` einen separat definierten Typ handelt, der die Art der Berechnungen charakterisiert, die kombiniert werden, z. B. für asynchrone Workflows und für Sequenzworkflows. Die Signaturen dieser Methoden ermöglichen es, sie miteinander zu kombinieren und zu verschachteln, sodass das von einem Konstrukt zurückgegebene Workflowobjekt an das nächste übergeben werden kann. Wenn der Compiler einen Berechnungsausdruck analysiert, konvertiert er den Ausdruck in eine Reihe von geschachtelten Funktionsaufrufen, indem er die Methoden in der vorherigen Tabelle und den Code im Berechnungsausdruck verwendet.

Der geschachtelte Ausdruck hat die folgende Form:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

Im obigen Code werden `Run` `Delay` die Aufrufe von und ausgelassen, wenn sie nicht in der Berechnungsausdruckbuilderklasse definiert sind. Der Text des Berechnungsausdrucks, `{| cexpr |}`hier als bezeichnet , wird durch die in der folgenden Tabelle beschriebenen Übersetzungen in Aufrufe übersetzt, die die Methoden der Builder-Klasse betreffen. Der Berechnungsausdruck `{| cexpr |}` wird rekursiv entsprechend diesen `expr` Übersetzungen definiert, wobei `cexpr` es sich um einen F-Ausdruck handelt und es sich um einen Berechnungsausdruck handelt.

|Ausdruck|Sprachübersetzung|
|----------|-----------|
|<code>{ let binding in cexpr }</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{ let! pattern = expr in cexpr }</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ do! expr in cexpr }</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{ yield expr }</code>|`builder.Yield(expr)`|
|<code>{ yield! expr }</code>|`builder.YieldFrom(expr)`|
|<code>{ return expr }</code>|`builder.Return(expr)`|
|<code>{ return! expr }</code>|`builder.ReturnFrom(expr)`|
|<code>{ use pattern = expr in cexpr }</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{ use! value = expr in cexpr }</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> { cexpr }))))</code>|
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else builder.Zero()</code>|
|<code>{ if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then { cexpr0 } else { cexpr1 }</code>|
|<code>{ match expr with &#124; pattern_i -> cexpr_i }</code>|<code>match expr with &#124; pattern_i -> { cexpr_i }</code>|
|<code>{ for pattern in expr do cexpr }</code>|<code>builder.For(enumeration, (fun pattern -> { cexpr }))</code>|
|<code>{ for identifier = expr1 to expr2 do cexpr }</code>|<code>builder.For(enumeration, (fun identifier -> { cexpr }))</code>|
|<code>{ while expr do cexpr }</code>|<code>builder.While(fun () -> expr, builder.Delay({ cexpr }))</code>|
|<code>{ try cexpr with &#124; pattern_i -> expr_i }</code>|<code>builder.TryWith(builder.Delay({ cexpr }), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{ try cexpr finally expr }</code>|<code>builder.TryFinally(builder.Delay( { cexpr }), (fun () -> expr))</code>|
|<code>{ cexpr1; cexpr2 }</code>|<code>builder.Combine({ cexpr1 }, { cexpr2 })</code>|
|<code>{ other-expr; cexpr }</code>|<code>expr; { cexpr }</code>|
|<code>{ other-expr }</code>|`expr; builder.Zero()`|

Beschreibt in der `other-expr` vorherigen Tabelle einen Ausdruck, der nicht anderweitig in der Tabelle aufgeführt ist. Eine Builderklasse muss nicht alle Methoden implementieren und alle in der vorherigen Tabelle aufgeführten Übersetzungen unterstützen. Die nicht implementierten Konstrukte sind in Berechnungsausdrücken dieses Typs nicht verfügbar. Wenn Sie z. B. das `use` Schlüsselwort in Ihren Berechnungsausdrücken `Use` nicht unterstützen möchten, können Sie die Definition in Ihrer Builderklasse weglassen.

Das folgende Codebeispiel zeigt einen Berechnungsausdruck, der eine Berechnung als eine Reihe von Schritten kapselt, die Schritt für Schritt ausgewertet werden können. Ein diskriminierter Union-Typ , `OkOrException`, kodiert den Fehlerstatus des Ausdrucks, wie bisher ausgewertet. Dieser Code veranschaulicht mehrere typische Muster, die Sie in Ihren Berechnungsausdrücken verwenden können, z. B. Boilerplate-Implementierungen einiger Builder-Methoden.

```fsharp
// Computations that can be run step by step
type Eventually<'T> =
    | Done of 'T
    | NotYetDone of (unit -> Eventually<'T>)

module Eventually =
    // The bind for the computations. Append 'func' to the
    // computation.
    let rec bind func expr =
        match expr with
        | Done value -> func value
        | NotYetDone work -> NotYetDone (fun () -> bind func (work()))

    // Return the final value wrapped in the Eventually type.
    let result value = Done value

    type OkOrException<'T> =
        | Ok of 'T
        | Exception of System.Exception

    // The catch for the computations. Stitch try/with throughout
    // the computation, and return the overall result as an OkOrException.
    let rec catch expr =
        match expr with
        | Done value -> result (Ok value)
        | NotYetDone work ->
            NotYetDone (fun () ->
                let res = try Ok(work()) with | exn -> Exception exn
                match res with
                | Ok cont -> catch cont // note, a tailcall
                | Exception exn -> result (Exception exn))

    // The delay operator.
    let delay func = NotYetDone (fun () -> func())

    // The stepping action for the computations.
    let step expr =
        match expr with
        | Done _ -> expr
        | NotYetDone func -> func ()

    // The rest of the operations are boilerplate.
    // The tryFinally operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryFinally expr compensation =
        catch (expr)
        |> bind (fun res ->
            compensation();
            match res with
            | Ok value -> result value
            | Exception exn -> raise exn)

    // The tryWith operator.
    // This is boilerplate in terms of "result", "catch", and "bind".
    let tryWith exn handler =
        catch exn
        |> bind (function Ok value -> result value | Exception exn -> handler exn)

    // The whileLoop operator.
    // This is boilerplate in terms of "result" and "bind".
    let rec whileLoop pred body =
        if pred() then body |> bind (fun _ -> whileLoop pred body)
        else result ()

    // The sequential composition operator.
    // This is boilerplate in terms of "result" and "bind".
    let combine expr1 expr2 =
        expr1 |> bind (fun () -> expr2)

    // The using operator.
    let using (resource: #System.IDisposable) func =
        tryFinally (func resource) (fun () -> resource.Dispose())

    // The forLoop operator.
    // This is boilerplate in terms of "catch", "result", and "bind".
    let forLoop (collection:seq<_>) func =
        let ie = collection.GetEnumerator()
        tryFinally
            (whileLoop
                (fun () -> ie.MoveNext())
                (delay (fun () -> let value = ie.Current in func value)))
            (fun () -> ie.Dispose())

// The builder class.
type EventuallyBuilder() =
    member x.Bind(comp, func) = Eventually.bind func comp
    member x.Return(value) = Eventually.result value
    member x.ReturnFrom(value) = value
    member x.Combine(expr1, expr2) = Eventually.combine expr1 expr2
    member x.Delay(func) = Eventually.delay func
    member x.Zero() = Eventually.result ()
    member x.TryWith(expr, handler) = Eventually.tryWith expr handler
    member x.TryFinally(expr, compensation) = Eventually.tryFinally expr compensation
    member x.For(coll:seq<_>, func) = Eventually.forLoop coll func
    member x.Using(resource, expr) = Eventually.using resource expr

let eventually = new EventuallyBuilder()

let comp = eventually {
    for x in 1..2 do
        printfn " x = %d" x
    return 3 + 4 }

// Try the remaining lines in F# interactive to see how this
// computation expression works in practice.
let step x = Eventually.step x

// returns "NotYetDone <closure>"
comp |> step

// prints "x = 1"
// returns "NotYetDone <closure>"
comp |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step
```

Ein Berechnungsausdruck hat einen zugrunde liegenden Typ, den der Ausdruck zurückgibt. Der zugrunde liegende Typ kann ein berechnetes Ergebnis oder eine verzögerte Berechnung darstellen, die durchgeführt werden kann, oder er kann eine Möglichkeit bieten, durch irgendeine Art von Auflistung zu iterieren. Im vorherigen Beispiel war der zugrunde liegende Typ **Eventually**. Bei einem Sequenzausdruck lautet <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>der zugrunde liegende Typ . Bei einem Abfrageausdruck lautet <xref:System.Linq.IQueryable?displayProperty=nameWithType>der zugrunde liegende Typ . Bei einem asynchronen Workflow lautet [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)der zugrunde liegende Typ . Das `Async` Objekt stellt die Arbeit dar, die zum Berechnen des Ergebnisses ausgeführt werden soll. Sie rufen z. B. auf, [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) um eine Berechnung auszuführen und das Ergebnis zurückzugeben.

## <a name="custom-operations"></a>Benutzerdefinierte Vorgänge

Sie können einen benutzerdefinierten Vorgang für einen Berechnungsausdruck definieren und einen benutzerdefinierten Vorgang als Operator in einem Berechnungsausdruck verwenden. Sie können z. B. einen Abfrageoperator in einen Abfrageausdruck einschließen. Wenn Sie einen benutzerdefinierten Vorgang definieren, müssen Sie die Methoden Yield und For im Berechnungsausdruck definieren. Um einen benutzerdefinierten Vorgang zu definieren, legen Sie ihn in [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)eine Builderklasse für den Berechnungsausdruck, und wenden Sie dann die an. Dieses Attribut verwendet eine Zeichenfolge als Argument, d. h. den Namen, der in einem benutzerdefinierten Vorgang verwendet werden soll. Dieser Name wird zu Beginn der öffnenden geschweiften Klammer des Berechnungsausdrucks in den Gültigkeitsbereich aufgenommen. Daher sollten Sie keine Bezeichner verwenden, die denselben Namen wie ein benutzerdefinierter Vorgang in diesem Block haben. Vermeiden Sie beispielsweise die Verwendung von `all` `last` Bezeichnern wie z. B. oder in Abfrageausdrücken.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Erweitern vorhandener Builder mit neuen Custom Operations

Wenn Sie bereits über eine Builderklasse verfügen, können die benutzerdefinierten Vorgänge von außerhalb dieser Builderklasse erweitert werden. Erweiterungen müssen in Modulen deklariert werden. Namespaces können keine Erweiterungsmember enthalten, außer in derselben Datei und derselben Namespacedeklarationsgruppe, in der der Typ definiert ist.

Das folgende Beispiel zeigt die `Microsoft.FSharp.Linq.QueryBuilder` Erweiterung der vorhandenen Klasse.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>Weitere Informationen

- [Sprachreferenz](index.md)
- [Asynchrone Workflows](asynchronous-workflows.md)
- [Sequenzen](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [Abfrageausdrücke](query-expressions.md)
