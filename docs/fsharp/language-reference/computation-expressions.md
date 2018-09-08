---
title: Berechnungsausdrücke (F#)
description: Erfahren Sie, wie Sie einfache Syntax für das Schreiben von Berechnungen in f#, die können sequenziert und kombiniert werden mithilfe von ablaufsteuerungskonstrukten und Bindungen erstellen.
ms.date: 07/27/2018
ms.openlocfilehash: ce81af7966a436b3973de277fb2a78ec06f4c471
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44200063"
---
# <a name="computation-expressions"></a>Berechnungsausdrücke

Berechnungsausdrücke in f# bieten eine bequeme Syntax für das Schreiben von Berechnungen, die sequenziert werden können und mithilfe von ablaufsteuerungskonstrukten und Bindungen kombiniert. Abhängig von der Art des Berechnungsausdrucks können sie als eine Möglichkeit, Monaden, Monoids, Monad Transformatoren und applicative Funktionselemente auszudrücken betrachtet werden. Anders als bei anderen Sprachen (z. B. *-Notation* in Haskell), sie sind nicht an eine einzelne Abstraktion gebunden, und verlassen Sie sich nicht in Makros oder anderen Formen der Metaprogrammierung, um eine praktische und kontextbezogene Syntax zu erreichen.

## <a name="overview"></a>Übersicht

Berechnungen können viele Formen annehmen. Die häufigste Form der Berechnung ist Singlethread-Ausführung, bei dem ist leicht zu verstehen und zu bearbeiten. Nicht alle Arten von Berechnungen sind jedoch so einfach wie das Singlethread-Ausführung. Beispiele:

* Nicht deterministische Berechnungen
* Asynchrone Berechnungen
* Effectful Berechnungen
* Produktive Berechnungen

Allgemeiner gesagt, es gibt *kontextbezogene* Berechnungen, die Sie in bestimmten Teilen einer Anwendung ausführen müssen. Schreiben von kontextbezogenen Code kann schwierig sein wie "Speicherverlusten" Berechnungen außerhalb von einem bestimmten Kontext ohne Abstraktionen, um zu verhindern, dass Sie auf diese Weise einfach ist. Diese Abstraktionen sind oft schwierig, selbst zu schreiben, die Grund f# eine verallgemeinerte Vorgehensweise hat sogenannte **Berechnungsausdrücke**.

Berechnungsausdrücke bieten ein einheitliches Syntax und Abstraktion Modell für die Codierung von kontextbezogener Berechnungen.

Jeder Ausdruck für die Berechnung basiert auf einer *Builder* Typ. Der Generatortyp definiert die Vorgänge, die für den Ausdruck für die Berechnung verfügbar sind. Finden Sie unter [erstellen einen neuen Typ von Ausdruck für die Berechnung](computation-expressions.md#creating-a-new-type-of-computation-expression), erfahren, wie Sie einen Ausdruck für die benutzerdefinierte Berechnung zu erstellen.

### <a name="syntax-overview"></a>Übersicht über die Syntax

Alle Berechnungsausdrücke aufweisen folgende Form:

```
builder-expr { cexper }
```

in denen `builder-expr` ist der Name eines Builder-Typs, der den Ausdruck für die Berechnung, definiert und `cexper` ist der Ausdruckstext, der den Ausdruck für die Berechnung. Z. B. `async` Ausdruckscode Berechnung kann wie folgt aussehen:

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

Es ist eine spezielle, zusätzliche-Syntax in einem Berechnungsausdruck verfügbar, wie im vorherigen Beispiel gezeigt. Die folgenden Ausdruck Formulare sind mit Berechnungsausdrücken möglich:

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

Jedes dieser Schlüsselwörter und andere standard F#-Schlüsselwörter sind nur in einem Berechnungsausdruck verfügbar, wenn sie in den unterstützenden-Generator-Typ definiert wurden. Die einzige Ausnahme hierbei ist `match!`, dies ist selbst die Syntax-Zuckerguss für die Verwendung von `let!` gefolgt von einer Musterübereinstimmung auf dem Ergebnis.

Der Generator kann ein Objekt, das spezielle Methoden definiert, die steuern, die Möglichkeit, die die Fragmente des Berechnungsausdrucks kombiniert werden. d. h. seine Methoden Berechnungsausdrucks Verhalten steuern. Eine weitere Möglichkeit zum Beschreiben einer Zeichenfolgengenerator-Klasse ist zu sagen, dass Sie den Vorgang, der viele F#-Konstrukte, beispielsweise Schleifen und Bindungen anpassen können.

### `let!`

Die `let!` -Schlüsselwort bindet das Ergebnis eines Aufrufs von einem anderen Berechnungsausdruck an einen Namen:

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

Wenn Sie den Aufruf von einem Berechnungsausdruck mit binden `let`, erhalten Sie nicht das Ergebnis des Berechnungsausdrucks. Stattdessen wird gebunden den Wert des der *realisierten* aufrufen, um dieser Ausdruck für die Berechnung. Verwendung `let!` zum Binden an das Ergebnis.

`let!` wird definiert, indem die `Bind(x, f)` Member für den Generatortyp.

### `do!`

Die `do!` -Schlüsselwort ist für einen Ausdruck für die Berechnung aufrufen, gibt eine `unit`-wie (von definiert die `Zero` Member für den Generator):

```fsharp
let doThingsAsync data url =
    async {
        do! sumbitData data url
        ...
    }
```

Für die [asynchrone Workflows](asynchronous-workflows.md), dieser Typ ist `Async<unit>`. Der Typ ist wahrscheinlich für die anderen Berechnungsausdrücken `CExpType<unit>`.

`do!` wird definiert, indem die `Bind(x, f)` Member für den Generatortyp, in denen `f` erzeugt eine `unit`.

### `yield`

Die `yield` -Schlüsselwort ist für die Rückgabe eines Werts aus den Berechnungsausdruck, damit es als verwendet werden kann ein <xref:System.Collections.Generic.IEnumerable%601>:

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

Wie bei der [yield-Schlüsselwort in c#](../../csharp/language-reference/keywords/yield.md), jedes Element in den Ausdruck für die Berechnung wird zurückgegeben, zurück, wie sie durchlaufen wird.

`yield` wird definiert, indem die `Yield(x)` Member für den Generatortyp, in denen `x` ist das Element, um wieder zu erhalten.

### `yield!`

Die `yield!` -Schlüsselwort ist für das eine Auflistung von Werten aus einem Berechnungsausdruck reduzieren:

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

Bei der Auswertung, bezeichnet der Ausdruck für die Berechnung von `yield!` werden haben die Elemente zurückgegeben, die Back-nacheinander, vereinfachen das Ergebnis.

`yield!` wird definiert, indem die `YieldFrom(x)` Member für den Generatortyp, in denen `x` ist eine Auflistung von Werten.

### `return`

Die `return` Schlüsselwort umschließt einen Wert in den Typ, des Berechnungsausdrucks entspricht. Abgesehen von der von Berechnungsausdrücken mit `yield`, er wird verwendet, um "einen Ausdruck für die Berechnung abgeschlossen werden":

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return` wird definiert, indem die `Return(x)` Member für den Generatortyp, in denen `x` ist das Element zu umschließen.

### `return!`

Die `return!` Schlüsselwort erkennt, dass den Wert eines Ausdrucks für die Berechnung und dient als Wrapper für das Ergebnis in den Typ, des Berechnungsausdrucks entsprechen:

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

`return!` wird definiert, indem die `ReturnFrom(x)` Member für den Generatortyp, in denen `x` wird von einem anderen Berechnungsausdruck.

### `match!`

Ab f# 4.5, den `match!` Schlüsselwort ermöglicht Sie Inline einen Aufruf an eine andere Berechnung Ausdruck und das Muster abzugleichen, das Ergebnis:

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

Beim Aufrufen von eines Berechnungsausdrucks mit `match!`, sie werden feststellen, das Ergebnis des Aufrufs wie `let!`. Dies wird häufig verwendet, wenn einen Berechnungsausdruck aufrufen, ist das Ergebnis einer [optional](options.md).

## <a name="built-in-computation-expressions"></a>Integrierte Berechnungsausdrücke

Die F#-Kernbibliothek definiert drei integrierte Berechnungsausdrücke: [Sequenzausdrücke](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Abfrageausdrücke](query-expressions.md).

## <a name="creating-a-new-type-of-computation-expression"></a>Erstellen eine neue Art von Ausdruck für die Berechnung

Sie können die Merkmale der eigene Berechnungsausdrücke definieren, indem eine Generatorklasse erstellen und definieren bestimmte speziellen Methoden für die Klasse. Die Zeichenfolgengenerator-Klasse kann optional die Methoden definieren, wie in der folgenden Tabelle aufgeführt.

Die folgende Tabelle beschreibt die Methoden, die in einer Workflow-Generator-Klasse verwendet werden können.

|**Methode**|**Typische Signaturen**|**Beschreibung**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Wird aufgerufen, für die `let!` und `do!` im Berechnungsausdrücke.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Umschließt einen Ausdruck für die Berechnung als Funktion an.|
|`Return`|`'T -> M<'T>`|Wird aufgerufen, für die `return` im Berechnungsausdrücke.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Wird aufgerufen, für die `return!` im Berechnungsausdrücke.|
|`Run`|`M<'T> -> M<'T>` oder<br /><br />`M<'T> -> 'T`|Führt einen Ausdruck für die Berechnung an.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` oder<br /><br />`M<unit> * M<'T> -> M<'T>`|Wird aufgerufen, für die Sequenzierung im Berechnungsausdrücke.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` oder<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Wird aufgerufen, für die `for...do` Ausdrücke im Berechnungsausdrücke.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Wird aufgerufen, für die `try...finally` Ausdrücke im Berechnungsausdrücke.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Wird aufgerufen, für die `try...with` Ausdrücke im Berechnungsausdrücke.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|Wird aufgerufen, für die `use` Bindungen in Berechnungsausdrücke.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Wird aufgerufen, für die `while...do` Ausdrücke im Berechnungsausdrücke.|
|`Yield`|`'T -> M<'T>`|Wird aufgerufen, für die `yield` Ausdrücke im Berechnungsausdrücke.|
|`YieldFrom`|`M<'T> -> M<'T>`|Wird aufgerufen, für die `yield!` Ausdrücke im Berechnungsausdrücke.|
|`Zero`|`unit -> M<'T>`|Wird aufgerufen, für leere `else` branches `if...then` Ausdrücke im Berechnungsausdrücke.|

Viele der Methoden in einem Zeichenfolgengenerator-Klasse verwenden und Zurückgeben einer `M<'T>` Konstrukt, in der Regel separat definierten Typ, der die Art der Berechnungen, die kombiniert werden, z. B. charakterisiert, `Async<'T>` für asynchrone Workflows und `Seq<'T>` für die Sequenz-Workflows. Die Signaturen der folgenden Methoden ermöglichen ihnen kombiniert und mit untereinander geschachtelt werden sollen, damit der Workflow-Objekt, das von einem Konstrukt zurückgegebene zum nächsten übergeben werden kann. Der Compiler, wenn es sich um einen Ausdruck für die Berechnung, analysiert konvertiert den Ausdruck in eine Reihe von Aufrufe geschachtelter Funktionen mithilfe von Methoden in der obigen Tabelle und der Code in den Ausdruck für die Berechnung.

Der geschachtelte Ausdruck ist im folgenden Format:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

Im obigen Code, die Aufrufe an `Run` und `Delay` werden ausgelassen, wenn sie nicht in der Berechnung Ausdrucks-Generator-Klasse definiert sind. Der Text des Berechnungsausdrucks, hier bezeichnet als `{| cexpr |}`, durch die Übersetzungen, die in der folgenden Tabelle beschrieben in Aufrufe, die im Zusammenhang mit den Methoden der Builder-Klasse übersetzt. Der Ausdruck für die Berechnung `{| cexpr |}` wird definierten rekursiv nach diese Übersetzungen, in denen `expr` ist ein F#-Ausdruck und `cexpr` ist ein Ausdruck für die Berechnung.

|Ausdruck|Übersetzung|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}</code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|
In der vorherigen Tabelle `other-expr` wird beschrieben, einen Ausdruck, der andernfalls nicht in der Tabelle aufgeführt ist. Eine Zeichenfolgengenerator-Klasse muss nicht alle Methoden zu implementieren und unterstützen alle die Übersetzungen, die in der vorherigen Tabelle aufgeführt. Diese Konstrukte, die nicht implementiert werden, sind nicht verfügbar ist, im Berechnungsausdrücke dieses Typs. Angenommen, Sie nicht möchten, zur Unterstützung der `use` -Schlüsselwort in Berechnungsausdrücken, können Sie die Definition der weglassen `Use` in Ihre Zeichenfolgengenerator-Klasse.

Das folgende Codebeispiel zeigt einen Ausdruck für die Berechnung, der eine Berechnung kapselt, eine Reihe von Schritten, die sein können nur einem Schritt zu einem Zeitpunkt ausgewertet. Eine Unterscheidungs-union-Typs `OkOrException`, den Fehlerstatus des Ausdrucks codiert, wie bisher ausgewertet. Dieser Code zeigt einige typische Muster, die Sie in Ihrer Berechnungsausdrücken, z. B. Codebausteine Implementierung einiger der-Generator-Methoden verwenden können.

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
        | Done value -> NotYetDone (fun () -> func value)
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
// returns "NotYetDone <closure>"
comp |> step |> step |> step |> step |> step |> step

// prints "x = 1"
// prints "x = 2"
// returns "Done 7"
comp |> step |> step |> step |> step |> step |> step |> step |> step
```

Ein Ausdruck für die Berechnung hat einen zugrunde liegenden Typ, der der Ausdruck zurückgibt. Der zugrunde liegende Typ kann eine berechnete Ergebnis oder eine verzögerte Berechnung, die ausgeführt werden kann oder darstellen kann es eine Möglichkeit zum iterieren durch eine Art von Auflistung bereitstellen. Im vorherigen Beispiel wurde der zugrunde liegende Typ **schließlich**. Für einen Sequenzausdruck der zugrunde liegenden Typ ist <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Bei einem Abfrageausdruck, der zugrunde liegende Typ ist <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Ist ein asynchroner Workflow, der zugrunde liegenden Typ [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). Die `Async` Objekt darstellt, die Arbeit ausgeführt werden, um das Ergebnis zu berechnen. Rufen Sie z. B. [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) führen eine Berechnung, und geben das Ergebnis zurück.

## <a name="custom-operations"></a>Benutzerdefinierte Vorgänge

Sie können einen Vorgang auf einen Ausdruck für die Berechnung definieren und verwenden einen Vorgang als einen Operator in einem Ausdruck für die Berechnung. Beispielsweise können Sie einen Abfrageoperator in einem Abfrageausdruck einschließen. Wenn Sie einen Vorgang definieren, müssen Sie die "yield" definieren und für Methoden in den Ausdruck für die Berechnung. Um einen Vorgang zu definieren, fügen Sie ihn in eine Builder-Klasse für den Ausdruck für die Berechnung aus, und wenden Sie dann die [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Dieses Attribut akzeptiert eine Zeichenfolge als Argument, das heißt, die in einem benutzerdefinierten Vorgang verwendet werden. Dieser Name wird in den Bereich am Anfang der öffnenden geschweiften Klammer des Berechnungsausdrucks. Aus diesem Grund sollte nicht Sie Bezeichner mit den gleichen Namen wie einen Vorgang in diesem Block verwendet werden. Vermeiden Sie z. B. wie z. B. die Verwendung von Bezeichnern `all` oder `last` in Abfrageausdrücken.

### <a name="extending-existing-builders-with-new-custom-operations"></a>Erweitern Sie vorhandene Generatoren mit neuen benutzerdefinierten-Vorgänge

Wenn Sie bereits über ein Zeichenfolgengenerator-Klasse verfügen, können benutzerdefinierte Vorgänge außerhalb dieser Zeichenfolgengenerator-Klasse aus erweitert werden. Erweiterungen müssen in Modulen deklariert werden. Namespaces können nicht enthalten, Erweiterungsmember außer in der gleichen Datei und der gleichen Namespace-Deklaration-Gruppe, in denen der Typ definiert ist.

Das folgende Beispiel zeigt die Erweiterung des bestehenden `Microsoft.FSharp.Linq.QueryBuilder` Klasse.

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Asynchrone Workflows](asynchronous-workflows.md)
- [Sequenzen](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [Abfrageausdrücke](query-expressions.md)
