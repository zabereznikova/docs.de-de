---
title: Berechnungsausdrücke
description: 'Erfahren Sie, wie Sie eine bequeme Syntax zum Schreiben von Berechnungen in F # erstellen, die mithilfe von Ablaufsteuerungskonstrukten und Bindungen sequenziert und kombiniert werden können.'
ms.date: 08/15/2020
f1_keywords:
- let!_FS
ms.openlocfilehash: 1649d8c57ea9e025d40ef6d39d92b96795964150
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812158"
---
# <a name="computation-expressions"></a>Berechnungsausdrücke

Berechnungs Ausdrücke in F # bieten eine bequeme Syntax zum Schreiben von Berechnungen, die mithilfe von Ablaufsteuerungs-Konstrukten und-Bindungen sequenziert und kombiniert werden können. Abhängig von der Art des Berechnungs Ausdrucks können Sie sich als Möglichkeit vorstellen, Monads, Monoids, Monad-Transformatoren und Anwendungs Funktoren auszudrücken. Im Gegensatz zu anderen Sprachen (z. b. *do-Notation* in Haskell) sind Sie jedoch nicht an eine einzelne Abstraktion gebunden, und Sie verlassen sich nicht auf Makros oder andere Formen der Metaprogrammierung, um eine bequeme und kontextabhängige Syntax zu erreichen.

## <a name="overview"></a>Übersicht

Berechnungen können viele Formen annehmen. Die häufigste Form der Berechnung ist die Ausführung mit nur einem Thread, die leicht verständlich und geändert werden kann. Allerdings sind nicht alle Berechnungs Formen so einfach wie die Ausführung mit einem Thread. Beispiele hierfür sind:

- Nicht deterministische Berechnungen
- Asynchrone Berechnungen
- Effektive Berechnungen
- Generative Berechnungen

Im Allgemeinen gibt es *kontextabhängige* Berechnungen, die Sie in bestimmten Teilen einer Anwendung ausführen müssen. Das Schreiben von Kontext sensiblem Code kann eine Herausforderung darstellen, da es einfach ist, Berechnungen außerhalb eines bestimmten Kontexts ohne Abstraktionen zu "vermeiden, um dies zu verhindern. Diese Abstraktionen sind häufig schwierig zu schreiben, da F # eine generalisierte Methode zum Aufrufen von **Berechnungs Ausdrücken**hat.

Berechnungs Ausdrücke bieten ein einheitliches Syntax-und Abstraktions Modell zum Codieren kontextbezogener Berechnungen.

Jeder Berechnungs Ausdruck wird durch einen *Builder* -Typ unterstützt. Der Builder-Typ definiert die Vorgänge, die für den Berechnungs Ausdruck verfügbar sind. Weitere Informationen zum Erstellen eines benutzerdefinierten Berechnungs Ausdrucks finden Sie unter [Erstellen eines neuen Berechnungs Typs](computation-expressions.md#creating-a-new-type-of-computation-expression).

### <a name="syntax-overview"></a>Syntaxübersicht

Alle Berechnungs Ausdrücke weisen die folgende Form auf:

```fsharp
builder-expr { cexper }
```

dabei `builder-expr` ist der Name eines Generator Typs, der den Berechnungs Ausdruck definiert, und `cexper` ist der Ausdrucks Text des Berechnungs Ausdrucks. Beispielsweise `async` kann der Berechnungs Ausdrucks Code wie folgt aussehen:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

Es gibt eine spezielle, zusätzliche Syntax, die in einem Berechnungs Ausdruck verfügbar ist, wie im vorherigen Beispiel gezeigt. Die folgenden Ausdrucksformen sind mit Berechnungs Ausdrücken möglich:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Jedes dieser Schlüsselwörter und andere Standard-F #-Schlüsselwörter sind nur in einem Berechnungs Ausdruck verfügbar, wenn Sie im Unterstützungs Generator-Typ definiert wurden. Die einzige Ausnahme hierbei ist, bei der es `match!` sich selbst um syntaktische Sugar handelt, wenn `let!` eine Muster Übereinstimmung auf das Ergebnis folgt.

Der Builder-Typ ist ein Objekt, das spezielle Methoden definiert, die bestimmen, wie die Fragmente des Berechnungs Ausdrucks kombiniert werden. Das heißt, seine Methoden steuern, wie sich der Berechnungs Ausdruck verhält. Eine andere Möglichkeit, eine Builder-Klasse zu beschreiben, besteht darin, dass Sie den Vorgang vieler F #-Konstrukte, wie z. b. Schleifen und Bindungen, anpassen können.

### `let!`

Das- `let!` Schlüsselwort bindet das Ergebnis eines Aufrufens an einen anderen Berechnungs Ausdruck an einen Namen:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Wenn Sie den-Ausdruck an einen Berechnungs Ausdruck mit binden `let` , wird das Ergebnis des Berechnungs Ausdrucks nicht angezeigt. Stattdessen haben Sie den Wert des *nicht erkannten* Aufrufes an diesen Berechnungs Ausdruck gebunden. Verwenden `let!` Sie, um eine Bindung an das Ergebnis herzustellen.

`let!` wird vom- `Bind(x, f)` Member für den Builder-Typ definiert.

### `do!`

Das `do!` Schlüsselwort dient zum Aufrufen eines Berechnungs Ausdrucks, der einen `unit` -ähnlichen Typ zurückgibt (definiert durch den- `Zero` Member auf dem Generator):

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

Für den [Async-Workflow](asynchronous-workflows.md)ist dieser Typ `Async<unit>` . Bei anderen Berechnungs Ausdrücken ist der Typ wahrscheinlich `CExpType<unit>` .

`do!` wird vom- `Bind(x, f)` Member für den Builder-Typ definiert, wobei `f` eine erzeugt `unit` .

### `yield`

Das `yield` Schlüsselwort dient zum Zurückgeben eines Werts aus dem Berechnungs Ausdruck, sodass er als verwendet werden kann <xref:System.Collections.Generic.IEnumerable%601> :

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

In den meisten Fällen kann Sie von Aufrufern ausgelassen werden. Die gängigste Methode zum weglassen `yield` ist mit dem- `->` Operator:

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

Für komplexere Ausdrücke, die möglicherweise viele verschiedene Werte ergeben, und möglicherweise bedingt, kann das-Schlüsselwort einfach weggelassen werden:

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

Ebenso wie das [yield-Schlüsselwort in c#](../../csharp/language-reference/keywords/yield.md)wird jedes Element im Berechnungs Ausdruck beim Durchlaufen zurückgegeben.

`yield` wird vom- `Yield(x)` Member für den Builder-Typ definiert, wobei `x` das Element ist, das zurückzugeben ist.

### `yield!`

Das `yield!` Schlüsselwort dient zum Vereinfachen einer Auflistung von Werten aus einem Berechnungs Ausdruck:

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

Bei der Auswertung werden die Elemente des von aufgerufenen Berechnungs Ausdrucks `yield!` nacheinander zurückgegeben und das Ergebnis vereinfacht.

`yield!` wird vom- `YieldFrom(x)` Member für den Builder-Typ definiert, wobei `x` eine Auflistung von-Werten ist.

Anders `yield` als `yield!` muss explizit angegeben werden. Das Verhalten ist in Berechnungs Ausdrücken nicht implizit.

### `return`

Das- `return` Schlüsselwort umschließt einen Wert in dem Typ, der dem Berechnungs Ausdruck entspricht. Abgesehen von Berechnungs Ausdrücken mit `yield` wird es verwendet, um einen Berechnungs Ausdruck zu vervollständigen:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return` wird vom- `Return(x)` Member für den Builder-Typ definiert, wobei `x` das zu Umbruch Ende Element ist.

### `return!`

Das `return!` Schlüsselwort erkennt den Wert eines Berechnungs Ausdrucks und umschließt das Ergebnis in den Typ, der dem Berechnungs Ausdruck entspricht:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!` wird vom- `ReturnFrom(x)` Member für den Builder-Typ definiert, wobei `x` ein anderer Berechnungs Ausdruck ist.

### `match!`

Mit dem `match!` -Schlüsselwort können Sie einen aufzurufenden Berechnungs Ausdruck und eine Muster Übereinstimmung im Ergebnis Inline ausführen:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

Wenn Sie einen Berechnungs Ausdruck mit aufrufen `match!` , wird das Ergebnis des Aufrufs wie erkannt `let!` . Dies wird häufig beim Aufrufen eines Berechnungs Ausdrucks verwendet, bei dem das Ergebnis [optional](options.md)ist.

## <a name="built-in-computation-expressions"></a>Integrierte Berechnungs Ausdrücke

Die F #-Kernbibliothek definiert drei integrierte Berechnungs Ausdrücke: [Sequenz Ausdrücke](sequences.md), [asynchrone Workflows](asynchronous-workflows.md)und [Abfrage Ausdrücke](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Erstellen eines neuen Typs des Berechnungs Ausdrucks

Sie können die Merkmale ihrer eigenen Berechnungs Ausdrücke definieren, indem Sie eine Builder-Klasse erstellen und bestimmte spezielle Methoden für die Klasse definieren. Die Builder-Klasse kann optional die Methoden wie in der folgenden Tabelle aufgeführt definieren.

In der folgenden Tabelle werden die Methoden beschrieben, die in einer Workflow Generator-Klasse verwendet werden können.

|**Methode**|**Typische Signatur (en)**|**Beschreibung**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Wird für `let!` und `do!` in Berechnungs Ausdrücken aufgerufen.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Umschließt einen Berechnungs Ausdruck als Funktion.|
|`Return`|`'T -> M<'T>`|Wird für `return` in Berechnungs Ausdrücken aufgerufen.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Wird für `return!` in Berechnungs Ausdrücken aufgerufen.|
|`Run`|`M<'T> -> M<'T>` oder<br /><br />`M<'T> -> 'T`|Führt einen Berechnungs Ausdruck aus.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` oder<br /><br />`M<unit> * M<'T> -> M<'T>`|Wird für die Sequenzierung in Berechnungs Ausdrücken aufgerufen.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` oder<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Wird für `for...do` Ausdrücke in Berechnungs Ausdrücken aufgerufen.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Wird für `try...finally` Ausdrücke in Berechnungs Ausdrücken aufgerufen.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Wird für `try...with` Ausdrücke in Berechnungs Ausdrücken aufgerufen.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|Wird für `use` Bindungen in Berechnungs Ausdrücken aufgerufen.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Wird für `while...do` Ausdrücke in Berechnungs Ausdrücken aufgerufen.|
|`Yield`|`'T -> M<'T>`|Wird für `yield` Ausdrücke in Berechnungs Ausdrücken aufgerufen.|
|`YieldFrom`|`M<'T> -> M<'T>`|Wird für `yield!` Ausdrücke in Berechnungs Ausdrücken aufgerufen.|
|`Zero`|`unit -> M<'T>`|Wird für leere `else` Verzweigungen von `if...then` Ausdrücken in Berechnungs Ausdrücken aufgerufen.|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|Gibt an, dass der Berechnungs Ausdruck als Anführungszeichen an den Member übermittelt wird `Run` . Dabei werden alle Instanzen einer Berechnung in ein Anführungszeichen übersetzt.|

Viele der Methoden in einer Generator-Klasse verwenden und geben ein `M<'T>` Konstrukt zurück. Hierbei handelt es sich in der Regel um einen separat definierten Typ, der die Art der zu kombinierenden Berechnungen, z `Async<'T>` . b. für asynchrone Workflows und `Seq<'T>` für Sequenz Workflows, charakterisiert. Mit den Signaturen dieser Methoden können Sie kombiniert und miteinander verknüpft werden, sodass das von einem Konstrukt zurückgegebene Workflow Objekt an das nächste weitergegeben werden kann. Wenn der Compiler einen Berechnungs Ausdruck analysiert, konvertiert er den Ausdruck in eine Reihe von geschalbten Funktionsaufrufen, indem er die Methoden in der vorangehenden Tabelle und den Code im Berechnungs Ausdruck verwendet.

Der-Ausdruck hat die folgende Form:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

Im obigen Code werden die Aufrufe von `Run` und `Delay` ausgelassen, wenn Sie in der Berechnungs Ausdrucks-Generator-Klasse nicht definiert sind. Der Text des Berechnungs Ausdrucks, der hier als bezeichnet wird, `{| cexpr |}` wird in Aufrufe mit den Methoden der Builder-Klasse durch die in der folgenden Tabelle beschriebenen Übersetzungen übersetzt. Der Berechnungs Ausdruck `{| cexpr |}` wird rekursiv gemäß diesen Übersetzungen definiert, wobei `expr` ein F #-Ausdruck und `cexpr` ein Berechnungs Ausdruck ist.

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

In der vorherigen Tabelle wird `other-expr` ein Ausdruck beschrieben, der in der Tabelle nicht anderweitig aufgeführt ist. Eine Builder-Klasse muss nicht alle Methoden implementieren und alle in der vorherigen Tabelle aufgeführten Übersetzungen unterstützen. Diese Konstrukte, die nicht implementiert werden, sind in Berechnungs Ausdrücken dieses Typs nicht verfügbar. Wenn Sie z. b. das- `use` Schlüsselwort in ihren Berechnungs Ausdrücken nicht unterstützen möchten, können Sie die Definition von `Use` in der Builder-Klasse weglassen.

Das folgende Codebeispiel zeigt einen Berechnungs Ausdruck, der eine Berechnung als eine Reihe von Schritten kapselt, die jeweils nacheinander ausgewertet werden können. Ein Unterscheidungs-Union-Typ `OkOrException` codiert den Fehlerzustand des Ausdrucks, der bisher ausgewertet wurde. In diesem Code werden mehrere typische Muster veranschaulicht, die Sie in ihren Berechnungs Ausdrücken verwenden können, wie z. b. die Implementierung von Code Bausteinen einiger Generator-Methoden.

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

Ein Berechnungs Ausdruck verfügt über einen zugrunde liegenden Typ, der vom Ausdruck zurückgegeben wird. Der zugrunde liegende Typ kann ein berechnetes Ergebnis oder eine verzögerte Berechnung darstellen, die durchgeführt werden kann, oder es kann eine Möglichkeit bieten, einen Auflistungstyp zu durchlaufen. Im vorherigen Beispiel war der zugrunde liegende Typ **schließlich**. Bei einem Sequenz Ausdruck ist der zugrunde liegende Typ <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> . Bei einem Abfrage Ausdruck ist der zugrunde liegende Typ <xref:System.Linq.IQueryable?displayProperty=nameWithType> . Bei einem asynchronen Workflow ist der zugrunde liegende Typ [`Async`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync-1.html) . Das- `Async` Objekt stellt die Arbeit dar, die zum Berechnen des Ergebnisses ausgeführt werden soll. Beispielsweise wird aufgerufen, [`Async.RunSynchronously`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-control-fsharpasync.html#RunSynchronously) um eine Berechnung auszuführen und das Ergebnis zurückzugeben.

## <a name="custom-operations"></a>Benutzerdefinierte Vorgänge

Sie können einen benutzerdefinierten Vorgang für einen Berechnungs Ausdruck definieren und einen benutzerdefinierten Vorgang als Operator in einem Berechnungs Ausdruck verwenden. Beispielsweise können Sie einen Abfrage Operator in einen Abfrage Ausdruck einschließen. Wenn Sie einen benutzerdefinierten Vorgang definieren, müssen Sie die Yield-und for-Methoden im Berechnungs Ausdruck definieren. Um einen benutzerdefinierten Vorgang zu definieren, fügen Sie ihn in eine Builder-Klasse für den Berechnungs Ausdruck ein, und wenden Sie dann das an [`CustomOperationAttribute`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-customoperationattribute.html) . Dieses Attribut verwendet eine Zeichenfolge als Argument. Dies ist der Name, der in einem benutzerdefinierten Vorgang verwendet werden soll. Dieser Name tritt am Anfang der öffnenden geschweiften Klammer des Berechnungs Ausdrucks auf. Daher sollten Sie keine Bezeichner verwenden, die denselben Namen wie ein benutzerdefinierter Vorgang in diesem Block haben. Vermeiden Sie z. b. die Verwendung von bezeichlern wie `all` oder `last` in Abfrage Ausdrücken.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Erweitern vorhandener Generatoren mit neuen benutzerdefinierten Vorgängen

Wenn Sie bereits über eine Builder-Klasse verfügen, können die benutzerdefinierten Vorgänge von außerhalb dieser Builder-Klasse erweitert werden. Erweiterungen müssen in Modulen deklariert werden. Namespaces dürfen keine Erweiterungs Elemente enthalten, außer in derselben Datei und derselben Namespace-Deklarations Gruppe, in der der Typ definiert ist.

Das folgende Beispiel zeigt die Erweiterung der vorhandenen- `FSharp.Linq.QueryBuilder` Klasse.

```fsharp
type FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [Asynchrone Workflows](asynchronous-workflows.md)
- [Sequenzen](sequences.md)
- [Abfrageausdrücke](query-expressions.md)
