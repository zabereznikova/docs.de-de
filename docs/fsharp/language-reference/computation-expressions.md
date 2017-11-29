---
title: "Berechnungsausdrücke (F#)"
description: "Informationen Sie zum Erstellen zweckmäßigen Syntax zum Schreiben von Berechnungen in F# erläutert, die während Ihrer Sequenzierung werden können und mit Control Flow Konstrukte und Bindungen kombiniert."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: acabbf5d-fbb8-479f-894c-7251bf16c8c3
ms.openlocfilehash: 15ba2e167efc1d295d81439dcf85bc7272e05265
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="computation-expressions"></a>Berechnungsausdrücke

Berechnungsausdrücke in f# bieten eine bequeme Syntax zum Schreiben von Berechnungen, die während Ihrer Sequenzierung werden können und mit Control Flow Konstrukte und Bindungen kombiniert. Sie können verwendet werden, um einen zweckmäßigen Syntax für bereitzustellen *Monads*, eine Funktion für funktionale Programmierung, die zum Verwalten von Daten, Steuerelement und Nebeneffekte in funktionalen Programmen verwendet werden kann.


## <a name="built-in-workflows"></a>Integrierte Workflows
Sequenzausdrücke sind ein Beispiel für einen Ausdruck für die Berechnung, wie asynchrone Workflows und Abfrageausdrücke sind. Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Abfrageausdrücke](query-expressions.md).

Bestimmte Funktionen gelten für Sequenzausdrücke und asynchrone Workflows und veranschaulicht die grundlegende Syntax für einen Ausdruck für die Berechnung:

```fsharp
builder-name { expression }
```

Die vorherige Syntax gibt an, dass der angegebene Ausdruck angegeben werden, indem Sie einen Ausdruck für die Berechnung *-Generator-Name*. Der Ausdruck für die Berechnung kann ein integrierter Workflow sein, z. B. `seq` oder `async`, oder es kann etwas Sie definieren. Die *-Generator-Name* ist der Bezeichner für eine Instanz eines speziellen Typs bekannt als die *Generatortyp*. Der Generatortyp ist ein Klassentyp, der spezielle Methoden, die steuern, wie die Fragmente des Berechnungsausdrucks definiert, d. h. Code kombiniert werden, die steuert, wie der Ausdruck ausgeführt wird. Eine weitere Möglichkeit zum Beschreiben einer Klasse Builder ist zu sagen, dass Sie den Vorgang, der viele F#-Konstrukte, wie beispielsweise Schleifen und Bindungen anpassen können.

In Berechnungsausdrücken sind zwei Formen für einige häufig verwendete Sprachkonstrukte verfügbar. Sie können die verschiedenen Konstrukte mit einer! (bang)-Suffix auf bestimmte Schlüsselwörter wie z. B. `let!`, `do!`und so weiter. Diese speziellen Formen dazu führen, dass bestimmte Funktionen, die definiert, in der Builder-Klasse, um den normalen integriertes Verhalten dieser Vorgänge zu ersetzen. Diese Formen ähneln den `yield!` Form der `yield` Schlüsselwort, das in Sequenzausdrücken verwendet wird. Weitere Informationen finden Sie unter [Sequenzen](sequences.md).


## <a name="creating-a-new-type-of-computation-expression"></a>Erstellen eine neue Art von Ausdruck für die Berechnung
Sie können die Merkmale der eigene Berechnungsausdrücke definieren, indem eine Generatorklasse erstellen und bestimmte speziellen Methoden definieren, für die Klasse. Die Builder-Klasse kann optional die Methoden definieren, wie in der folgenden Tabelle aufgeführt.

Die folgende Tabelle beschreibt die Methoden, die in einer Workflow-Generator-Klasse verwendet werden können.


|**Methode**|**Typische Signaturen**|**Beschreibung**|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|Wird aufgerufen, für `let!` und `do!` im Berechnungsausdrücke.|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|Umschließt einen Ausdruck für die Berechnung als Funktion an.|
|`Return`|`'T -> M<'T>`|Wird aufgerufen, für die `return` im Berechnungsausdrücke.|
|`ReturnFrom`|`M<'T> -> M<'T>`|Wird aufgerufen, für die `return!` im Berechnungsausdrücke.|
|`Run`|`M<'T> -> M<'T>` oder<br /><br />`M<'T> -> 'T`|Führt einen Ausdruck für die Berechnung an.|
|`Combine`|`M<'T> * M<'T> -> M<'T>` oder<br /><br />`M<unit> * M<'T> -> M<'T>`|Für die Sequenzierung in Berechnungsausdrücken aufgerufen.|
|`For`|`seq<'T> * ('T -> M<'U>) -> M<'U>` oder<br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|Wird aufgerufen, für `for...do` Ausdrücke im Berechnungsausdrücke.|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|Wird aufgerufen, für `try...finally` Ausdrücke im Berechnungsausdrücke.|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|Wird aufgerufen, für `try...with` Ausdrücke im Berechnungsausdrücke.|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|Wird aufgerufen, für `use` Bindungen in Berechnungsausdrücke.|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|Wird aufgerufen, für `while...do` Ausdrücke im Berechnungsausdrücke.|
|`Yield`|`'T -> M<'T>`|Wird aufgerufen, für `yield` Ausdrücke im Berechnungsausdrücke.|
|`YieldFrom`|`M<'T> -> M<'T>`|Wird aufgerufen, für `yield!` Ausdrücke im Berechnungsausdrücke.|
|`Zero`|`unit -> M<'T>`|Wird aufgerufen, für leere `else` Verzweigungen `if...then` Ausdrücke im Berechnungsausdrücke.|
Viele der Methoden in einer Klasse Builder verwenden und Zurückgeben einer `M<'T>` Konstrukt, das in der Regel separat definierten Typ, z. B. die Art der Berechnungen kombiniert wird, kennzeichnet, `Async<'T>` für asynchrone Workflows und `Seq<'T>` für die Sequenz-Workflows. Die Signaturen der folgenden Methoden aktivieren sie kombiniert und miteinander geschachtelt werden sollen, sodass das Workflowobjekt, das von einem Konstrukt zurückgegebene an die nächste übergeben werden kann. Der Compiler, wenn es sich um einen Ausdruck für die Berechnung, analysiert, die dem Ausdruck in eine Reihe von verschachtelten Funktionsaufrufe mithilfe der Methoden in der obigen Tabelle und den Code in den Ausdruck für die Berechnung konvertiert wird.

Der geschachtelte Ausdruck wird im folgenden Format:

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

Im obigen Code, der Aufrufe an `Run` und `Delay` werden ausgelassen, wenn sie nicht in der Berechnung Ausdrucks-Generator-Klasse definiert sind. Der Text des Berechnungsausdrucks, hier gekennzeichnet als `{| cexpr |}`, durch die in der folgenden Tabelle beschriebenen Übersetzungen in Aufrufe, die im Zusammenhang mit den Methoden der Klasse Builder übersetzt. Berechnungsausdrucks `{| cexpr |}` wird gemäß diese Übersetzungen definierten rekursiv, in denen `expr` ist ein f#-Ausdruck und `cexpr` ist ein Ausdruck für die Berechnung.



|Ausdruck|Übersetzung|
|----------|-----------|
|<code>{&#124; let binding in cexpr &#124;}</code>|<code>let binding in {&#124; cexpr &#124;}</code>|
|<code>{&#124; let! pattern = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; do! expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun () -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; yield expr &#124;}</code>|`builder.Yield(expr)`|
|<code>{&#124; yield! expr &#124;}</code>|`builder.YieldFrom(expr)`|
|<code>{&#124; return expr &#124;}<code>|`builder.Return(expr)`|
|<code>{&#124; return! expr &#124;}</code>|`builder.ReturnFrom(expr)`|
|<code>{&#124; use pattern = expr in cexpr &#124;}</code>|<code>builder.Using(expr, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; use! value = expr in cexpr &#124;}</code>|<code>builder.Bind(expr, (fun value -> builder.Using(value, (fun value -> {&#124; cexpr &#124;}))))</code>|
|<code>{&#124; if expr then cexpr0 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else binder.Zero()</code>|
|<code>{&#124; if expr then cexpr0 else cexpr1 &#124;}</code>|<code>if expr then {&#124; cexpr0 &#124;} else {&#124; cexpr1 &#124;}</code>|
|<code>{&#124; match expr with &#124; pattern_i -> cexpr_i &#124;}</code>|<code>match expr with &#124; pattern_i -> {&#124; cexpr_i &#124;}</code>|
|<code>{&#124; for pattern in expr do cexpr &#124;}</code>|<code>builder.For(enumeration, (fun pattern -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; for identifier = expr1 to expr2 do cexpr &#124;}<code>|<code>builder.For(enumeration, (fun identifier -> {&#124; cexpr &#124;}))</code>|
|<code>{&#124; while expr do cexpr &#124;}</code>|<code>builder.While(fun () -> expr), builder.Delay({&#124;cexpr &#124;})</code>|
|<code>{&#124; try cexpr with &#124; pattern_i -> expr_i &#124;}</code>|<code>builder.TryWith(builder.Delay({&#124; cexpr &#124;}), (fun value -> match value with &#124; pattern_i -> expr_i &#124; exn -> reraise exn)))</code>|
|<code>{&#124; try cexpr finally expr &#124;}</code>|<code>builder.TryFinally(builder.Delay( {&#124; cexpr &#124;}), (fun () -> expr))</code>|
|<code>{&#124; cexpr1; cexpr2 &#124;}</code>|<code>builder.Combine({&#124;cexpr1 &#124;}, {&#124; cexpr2 &#124;})</code>|
|<code>{&#124; other-expr; cexpr &#124;}</code>|<code>expr; {&#124; cexpr &#124;}</code>|
|<code>{&#124; other-expr &#124;}</code>|`expr; builder.Zero()`|
In der vorherigen Tabelle `other-expr` beschreibt einen Ausdruck, der nicht anderweitig in der Tabelle aufgeführt ist. Eine Generatorklasse muss nicht alle Methoden zu implementieren und unterstützen alle die Übersetzungen in der obigen Tabelle aufgeführt. Diese Konstrukte, die nicht implementiert werden sind nicht verfügbar in Berechnungsausdrücken dieses Typs. Angenommen, wenn Sie nicht möchten, zur Unterstützung der `use` -Schlüsselwort in Berechnungsausdrücken, können Sie die Definition der weglassen `Use` in Ihrer Builder-Klasse.

Das folgende Codebeispiel zeigt einen Ausdruck für die Berechnung, der eine Berechnung kapselt, eine Reihe von Schritten, die sein können einem Schritt zu einem Zeitpunkt ausgewertet. Eine Unterscheidungs-union-Typs `OkOrException`, codiert im Zustand "Fehler" des Ausdrucks wie bisher ausgewertet. Dieser Code veranschaulicht mehrere typische Muster, die Sie in Ihrer Berechnungsausdrücken, z. B. Textbaustein Implementierung einiger der Generator-Methoden verwenden können.

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

Ein Ausdruck für die Berechnung hat einen zugrunde liegenden Typ, der der Ausdruck zurückgibt. Möglicherweise des zugrunde liegenden Typs darstellen, eine berechnete Ergebnis oder eine verzögerte Berechnung, die ausgeführt werden kann kann, oder es eine Möglichkeit, eine Art von Auflistung durchlaufen. Im vorherigen Beispiel wurde der zugrunde liegende Typ **schließlich**. Für einen Sequenzausdruck der zugrunde liegenden Typ ist <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>. Bei einem Abfrageausdruck, der zugrunde liegende Typ ist <xref:System.Linq.IQueryable?displayProperty=nameWithType>. Für einen Workflow asychronen des zugrunde liegenden Typs ist [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7). Die `Async` Objekt darstellt, die Arbeit ausgeführt werden, um das Ergebnis zu berechnen. Rufen Sie z. B. [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) zum Ausführen einer Berechnung und das Ergebnis zurückgeben.

## <a name="custom-operations"></a>Benutzerdefinierte Funktionen
Sie können einen Vorgang auf einem Ausdruck für die Berechnung definieren und einen Vorgang als einen Operator in einem Ausdruck für die Berechnung. Beispielsweise können Sie einen Abfrage-Operator in einem Abfrageausdruck einschließen. Wenn Sie einen Vorgang definieren, müssen Sie die Yield definieren und für Methoden in den Ausdruck für die Berechnung. Um einen Vorgang zu definieren, fügen Sie ihn in eine Generatorklasse für den Ausdruck für die Berechnung aus, und wenden Sie dann die [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19). Dieses Attribut akzeptiert eine Zeichenfolge als ein Argument, das den Namen in einen Vorgang vorgesehen ist. Dieser Name wird in den Bereich am Anfang der öffnenden geschweiften Klammer des Berechnungsausdrucks. Aus diesem Grund darf keine Sie Bezeichner mit den gleichen Namen wie eine benutzerdefinierte Vorgänge in diesem Block verwendet werden. Z. B. vermeiden, wie z. B. die Verwendung von Bezeichnern `all` oder `last` in Abfrageausdrücken.

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Asynchrone Workflows](asynchronous-workflows.md)

[Sequenzen](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[Abfrageausdrücke](query-expressions.md)
