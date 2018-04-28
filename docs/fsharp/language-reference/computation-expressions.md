---
title: Berechnungsausdrücke (F#)
description: Informationen Sie zum Erstellen zweckmäßigen Syntax zum Schreiben von Berechnungen in F# erläutert, die während Ihrer Sequenzierung werden können und mit Control Flow Konstrukte und Bindungen kombiniert.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 990ea509e4fef84d3e3ee37471b28e2b8d019fad
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="computation-expressions"></a><span data-ttu-id="fe1bd-103">Berechnungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="fe1bd-103">Computation Expressions</span></span>

<span data-ttu-id="fe1bd-104">Berechnungsausdrücke in f# bieten eine bequeme Syntax zum Schreiben von Berechnungen, die während Ihrer Sequenzierung werden können und mit Control Flow Konstrukte und Bindungen kombiniert.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="fe1bd-105">Sie können verwendet werden, um einen zweckmäßigen Syntax für bereitzustellen *Monads*, eine Funktion für funktionale Programmierung, die zum Verwalten von Daten, Steuerelement und Nebeneffekte in funktionalen Programmen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-105">They can be used to provide a convenient syntax for *monads*, a functional programming feature that can be used to manage data, control, and side effects in functional programs.</span></span>


## <a name="built-in-workflows"></a><span data-ttu-id="fe1bd-106">Integrierte Workflows</span><span class="sxs-lookup"><span data-stu-id="fe1bd-106">Built-in Workflows</span></span>
<span data-ttu-id="fe1bd-107">Sequenzausdrücke sind ein Beispiel für einen Ausdruck für die Berechnung, wie asynchrone Workflows und Abfrageausdrücke sind.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-107">Sequence expressions are an example of a computation expression, as are asynchronous workflows and query expressions.</span></span> <span data-ttu-id="fe1bd-108">Weitere Informationen finden Sie unter [Sequenzen](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [Abfrageausdrücke](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="fe1bd-108">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

<span data-ttu-id="fe1bd-109">Bestimmte Funktionen gelten für Sequenzausdrücke und asynchrone Workflows und veranschaulicht die grundlegende Syntax für einen Ausdruck für die Berechnung:</span><span class="sxs-lookup"><span data-stu-id="fe1bd-109">Certain features are common to both sequence expressions and asynchronous workflows and illustrate the basic syntax for a computation expression:</span></span>

```fsharp
builder-name { expression }
```

<span data-ttu-id="fe1bd-110">Die vorherige Syntax gibt an, dass der angegebene Ausdruck angegeben werden, indem Sie einen Ausdruck für die Berechnung *-Generator-Name*.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-110">The previous syntax specifies that the given expression is a computation expression of a type specified by *builder-name*.</span></span> <span data-ttu-id="fe1bd-111">Der Ausdruck für die Berechnung kann ein integrierter Workflow sein, z. B. `seq` oder `async`, oder es kann etwas Sie definieren.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-111">The computation expression can be a built-in workflow, such as `seq` or `async`, or it can be something you define.</span></span> <span data-ttu-id="fe1bd-112">Die *-Generator-Name* ist der Bezeichner für eine Instanz eines speziellen Typs bekannt als die *Generatortyp*.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-112">The *builder-name* is the identifier for an instance of a special type known as the *builder type*.</span></span> <span data-ttu-id="fe1bd-113">Der Generatortyp ist ein Klassentyp, der spezielle Methoden, die steuern, wie die Fragmente des Berechnungsausdrucks definiert, d. h. Code kombiniert werden, die steuert, wie der Ausdruck ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-113">The builder type is a class type that defines special methods that govern the way the fragments of the computation expression are combined, that is, code that controls how the expression executes.</span></span> <span data-ttu-id="fe1bd-114">Eine weitere Möglichkeit zum Beschreiben einer Klasse Builder ist zu sagen, dass Sie den Vorgang, der viele F#-Konstrukte, wie beispielsweise Schleifen und Bindungen anpassen können.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-114">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

<span data-ttu-id="fe1bd-115">In Berechnungsausdrücken sind zwei Formen für einige häufig verwendete Sprachkonstrukte verfügbar.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-115">In computation expressions, two forms are available for some common language constructs.</span></span> <span data-ttu-id="fe1bd-116">Sie können die verschiedenen Konstrukte mit einer!</span><span class="sxs-lookup"><span data-stu-id="fe1bd-116">You can invoke the variant constructs by using a !</span></span> <span data-ttu-id="fe1bd-117">(bang)-Suffix auf bestimmte Schlüsselwörter wie z. B. `let!`, `do!`und so weiter.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-117">(bang) suffix on certain keywords, such as `let!`, `do!`, and so on.</span></span> <span data-ttu-id="fe1bd-118">Diese speziellen Formen dazu führen, dass bestimmte Funktionen, die definiert, in der Builder-Klasse, um den normalen integriertes Verhalten dieser Vorgänge zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-118">These special forms cause certain functions defined in the builder class to replace the ordinary built-in behavior of these operations.</span></span> <span data-ttu-id="fe1bd-119">Diese Formen ähneln den `yield!` Form der `yield` Schlüsselwort, das in Sequenzausdrücken verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-119">These forms resemble the `yield!` form of the `yield` keyword that is used in sequence expressions.</span></span> <span data-ttu-id="fe1bd-120">Weitere Informationen finden Sie unter [Sequenzen](sequences.md).</span><span class="sxs-lookup"><span data-stu-id="fe1bd-120">For more information, see [Sequences](sequences.md).</span></span>


## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="fe1bd-121">Erstellen eine neue Art von Ausdruck für die Berechnung</span><span class="sxs-lookup"><span data-stu-id="fe1bd-121">Creating a New Type of Computation Expression</span></span>
<span data-ttu-id="fe1bd-122">Sie können die Merkmale der eigene Berechnungsausdrücke definieren, indem eine Generatorklasse erstellen und bestimmte speziellen Methoden definieren, für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-122">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="fe1bd-123">Die Builder-Klasse kann optional die Methoden definieren, wie in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-123">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="fe1bd-124">Die folgende Tabelle beschreibt die Methoden, die in einer Workflow-Generator-Klasse verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-124">The following table describes methods that can be used in a workflow builder class.</span></span>


|<span data-ttu-id="fe1bd-125">**Methode**</span><span class="sxs-lookup"><span data-stu-id="fe1bd-125">**Method**</span></span>|<span data-ttu-id="fe1bd-126">**Typische Signaturen**</span><span class="sxs-lookup"><span data-stu-id="fe1bd-126">**Typical signature(s)**</span></span>|<span data-ttu-id="fe1bd-127">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="fe1bd-127">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="fe1bd-128">Wird aufgerufen, für `let!` und `do!` im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-128">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="fe1bd-129">Umschließt einen Ausdruck für die Berechnung als Funktion an.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-129">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="fe1bd-130">Wird aufgerufen, für die `return` im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-130">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="fe1bd-131">Wird aufgerufen, für die `return!` im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-131">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="fe1bd-132">`M<'T> -> M<'T>` oder</span><span class="sxs-lookup"><span data-stu-id="fe1bd-132">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="fe1bd-133">Führt einen Ausdruck für die Berechnung an.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-133">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="fe1bd-134">`M<'T> * M<'T> -> M<'T>` oder</span><span class="sxs-lookup"><span data-stu-id="fe1bd-134">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="fe1bd-135">Für die Sequenzierung in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-135">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="fe1bd-136">`seq<'T> * ('T -> M<'U>) -> M<'U>` oder</span><span class="sxs-lookup"><span data-stu-id="fe1bd-136">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="fe1bd-137">Wird aufgerufen, für `for...do` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-137">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="fe1bd-138">Wird aufgerufen, für `try...finally` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-138">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="fe1bd-139">Wird aufgerufen, für `try...with` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-139">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="fe1bd-140">Wird aufgerufen, für `use` Bindungen in Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-140">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="fe1bd-141">Wird aufgerufen, für `while...do` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-141">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="fe1bd-142">Wird aufgerufen, für `yield` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-142">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="fe1bd-143">Wird aufgerufen, für `yield!` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-143">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="fe1bd-144">Wird aufgerufen, für leere `else` Verzweigungen `if...then` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-144">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
<span data-ttu-id="fe1bd-145">Viele der Methoden in einer Klasse Builder verwenden und Zurückgeben einer `M<'T>` Konstrukt, das in der Regel separat definierten Typ, z. B. die Art der Berechnungen kombiniert wird, kennzeichnet, `Async<'T>` für asynchrone Workflows und `Seq<'T>` für die Sequenz-Workflows.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-145">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="fe1bd-146">Die Signaturen der folgenden Methoden aktivieren sie kombiniert und miteinander geschachtelt werden sollen, sodass das Workflowobjekt, das von einem Konstrukt zurückgegebene an die nächste übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-146">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="fe1bd-147">Der Compiler, wenn es sich um einen Ausdruck für die Berechnung, analysiert, die dem Ausdruck in eine Reihe von verschachtelten Funktionsaufrufe mithilfe der Methoden in der obigen Tabelle und den Code in den Ausdruck für die Berechnung konvertiert wird.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-147">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="fe1bd-148">Der geschachtelte Ausdruck wird im folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="fe1bd-148">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="fe1bd-149">Im obigen Code, der Aufrufe an `Run` und `Delay` werden ausgelassen, wenn sie nicht in der Berechnung Ausdrucks-Generator-Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-149">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="fe1bd-150">Der Text des Berechnungsausdrucks, hier gekennzeichnet als `{| cexpr |}`, durch die in der folgenden Tabelle beschriebenen Übersetzungen in Aufrufe, die im Zusammenhang mit den Methoden der Klasse Builder übersetzt.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-150">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="fe1bd-151">Berechnungsausdrucks `{| cexpr |}` wird gemäß diese Übersetzungen definierten rekursiv, in denen `expr` ist ein f#-Ausdruck und `cexpr` ist ein Ausdruck für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-151">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>



|<span data-ttu-id="fe1bd-152">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="fe1bd-152">Expression</span></span>|<span data-ttu-id="fe1bd-153">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="fe1bd-153">Translation</span></span>|
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
<span data-ttu-id="fe1bd-154">In der vorherigen Tabelle `other-expr` beschreibt einen Ausdruck, der nicht anderweitig in der Tabelle aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-154">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="fe1bd-155">Eine Generatorklasse muss nicht alle Methoden zu implementieren und unterstützen alle die Übersetzungen in der obigen Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-155">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="fe1bd-156">Diese Konstrukte, die nicht implementiert werden sind nicht verfügbar in Berechnungsausdrücken dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-156">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="fe1bd-157">Angenommen, wenn Sie nicht möchten, zur Unterstützung der `use` -Schlüsselwort in Berechnungsausdrücken, können Sie die Definition der weglassen `Use` in Ihrer Builder-Klasse.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-157">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="fe1bd-158">Das folgende Codebeispiel zeigt einen Ausdruck für die Berechnung, der eine Berechnung kapselt, eine Reihe von Schritten, die sein können einem Schritt zu einem Zeitpunkt ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-158">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="fe1bd-159">Eine Unterscheidungs-union-Typs `OkOrException`, codiert im Zustand "Fehler" des Ausdrucks wie bisher ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-159">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="fe1bd-160">Dieser Code veranschaulicht mehrere typische Muster, die Sie in Ihrer Berechnungsausdrücken, z. B. Textbaustein Implementierung einiger der Generator-Methoden verwenden können.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-160">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="fe1bd-161">Ein Ausdruck für die Berechnung hat einen zugrunde liegenden Typ, der der Ausdruck zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-161">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="fe1bd-162">Möglicherweise des zugrunde liegenden Typs darstellen, eine berechnete Ergebnis oder eine verzögerte Berechnung, die ausgeführt werden kann kann, oder es eine Möglichkeit, eine Art von Auflistung durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-162">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="fe1bd-163">Im vorherigen Beispiel wurde der zugrunde liegende Typ **schließlich**.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-163">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="fe1bd-164">Für einen Sequenzausdruck der zugrunde liegenden Typ ist <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-164">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fe1bd-165">Bei einem Abfrageausdruck, der zugrunde liegende Typ ist <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-165">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="fe1bd-166">Für einen Workflow asychronen des zugrunde liegenden Typs ist [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="fe1bd-166">For an asychronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="fe1bd-167">Die `Async` Objekt darstellt, die Arbeit ausgeführt werden, um das Ergebnis zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-167">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="fe1bd-168">Rufen Sie z. B. [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) zum Ausführen einer Berechnung und das Ergebnis zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-168">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="fe1bd-169">Benutzerdefinierte Funktionen</span><span class="sxs-lookup"><span data-stu-id="fe1bd-169">Custom Operations</span></span>
<span data-ttu-id="fe1bd-170">Sie können einen Vorgang auf einem Ausdruck für die Berechnung definieren und einen Vorgang als einen Operator in einem Ausdruck für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-170">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="fe1bd-171">Beispielsweise können Sie einen Abfrage-Operator in einem Abfrageausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-171">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="fe1bd-172">Wenn Sie einen Vorgang definieren, müssen Sie die Yield definieren und für Methoden in den Ausdruck für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-172">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="fe1bd-173">Um einen Vorgang zu definieren, fügen Sie ihn in eine Generatorklasse für den Ausdruck für die Berechnung aus, und wenden Sie dann die [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="fe1bd-173">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="fe1bd-174">Dieses Attribut akzeptiert eine Zeichenfolge als ein Argument, das den Namen in einen Vorgang vorgesehen ist.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-174">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="fe1bd-175">Dieser Name wird in den Bereich am Anfang der öffnenden geschweiften Klammer des Berechnungsausdrucks.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-175">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="fe1bd-176">Aus diesem Grund darf keine Sie Bezeichner mit den gleichen Namen wie eine benutzerdefinierte Vorgänge in diesem Block verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-176">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="fe1bd-177">Z. B. vermeiden, wie z. B. die Verwendung von Bezeichnern `all` oder `last` in Abfrageausdrücken.</span><span class="sxs-lookup"><span data-stu-id="fe1bd-177">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

## <a name="see-also"></a><span data-ttu-id="fe1bd-178">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe1bd-178">See Also</span></span>
[<span data-ttu-id="fe1bd-179">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="fe1bd-179">F# Language Reference</span></span>](index.md)

[<span data-ttu-id="fe1bd-180">Asynchrone Workflows</span><span class="sxs-lookup"><span data-stu-id="fe1bd-180">Asynchronous Workflows</span></span>](asynchronous-workflows.md)

[<span data-ttu-id="fe1bd-181">Sequenzen</span><span class="sxs-lookup"><span data-stu-id="fe1bd-181">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)

[<span data-ttu-id="fe1bd-182">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="fe1bd-182">Query Expressions</span></span>](query-expressions.md)
