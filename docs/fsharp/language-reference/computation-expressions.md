---
title: Berechnungsausdrücke
description: Erfahren Sie, wie Sie einfache Syntax für das Schreiben von Berechnungen in F#, die können sequenziert und kombiniert werden mithilfe von ablaufsteuerungskonstrukten und Bindungen erstellen.
ms.date: 07/27/2018
ms.openlocfilehash: 79159146e24dc50f851c29e3cf7fffe892c6d196
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53610696"
---
# <a name="computation-expressions"></a><span data-ttu-id="eef63-103">Berechnungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="eef63-103">Computation Expressions</span></span>

<span data-ttu-id="eef63-104">Berechnungsausdrücke in F# bieten eine bequeme Syntax für das Schreiben von Berechnungen, die sequenziert werden können und mithilfe von ablaufsteuerungskonstrukten und Bindungen kombiniert.</span><span class="sxs-lookup"><span data-stu-id="eef63-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="eef63-105">Abhängig von der Art des Berechnungsausdrucks können sie als eine Möglichkeit, Monaden, Monoids, Monad Transformatoren und applicative Funktionselemente auszudrücken betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="eef63-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="eef63-106">Anders als bei anderen Sprachen (z. B. *-Notation* in Haskell), sie sind nicht an eine einzelne Abstraktion gebunden, und verlassen Sie sich nicht in Makros oder anderen Formen der Metaprogrammierung, um eine praktische und kontextbezogene Syntax zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="eef63-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="eef63-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="eef63-107">Overview</span></span>

<span data-ttu-id="eef63-108">Berechnungen können viele Formen annehmen.</span><span class="sxs-lookup"><span data-stu-id="eef63-108">Computations can take many forms.</span></span> <span data-ttu-id="eef63-109">Die häufigste Form der Berechnung ist Singlethread-Ausführung, bei dem ist leicht zu verstehen und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="eef63-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="eef63-110">Nicht alle Arten von Berechnungen sind jedoch so einfach wie das Singlethread-Ausführung.</span><span class="sxs-lookup"><span data-stu-id="eef63-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="eef63-111">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="eef63-111">Some examples include:</span></span>

* <span data-ttu-id="eef63-112">Nicht deterministische Berechnungen</span><span class="sxs-lookup"><span data-stu-id="eef63-112">Non-deterministic computations</span></span>
* <span data-ttu-id="eef63-113">Asynchrone Berechnungen</span><span class="sxs-lookup"><span data-stu-id="eef63-113">Asynchronous computations</span></span>
* <span data-ttu-id="eef63-114">Effectful Berechnungen</span><span class="sxs-lookup"><span data-stu-id="eef63-114">Effectful computations</span></span>
* <span data-ttu-id="eef63-115">Produktive Berechnungen</span><span class="sxs-lookup"><span data-stu-id="eef63-115">Generative computations</span></span>

<span data-ttu-id="eef63-116">Allgemeiner gesagt, es gibt *kontextbezogene* Berechnungen, die Sie in bestimmten Teilen einer Anwendung ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="eef63-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="eef63-117">Schreiben von kontextbezogenen Code kann schwierig sein wie "Speicherverlusten" Berechnungen außerhalb von einem bestimmten Kontext ohne Abstraktionen, um zu verhindern, dass Sie auf diese Weise einfach ist.</span><span class="sxs-lookup"><span data-stu-id="eef63-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="eef63-118">Diese Abstraktionen sind oft schwierig, selbst zu schreiben, die Grund F# eine verallgemeinerte Vorgehensweise hat sogenannte **Berechnungsausdrücke**.</span><span class="sxs-lookup"><span data-stu-id="eef63-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="eef63-119">Berechnungsausdrücke bieten ein einheitliches Syntax und Abstraktion Modell für die Codierung von kontextbezogener Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="eef63-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="eef63-120">Jeder Ausdruck für die Berechnung basiert auf einer *Builder* Typ.</span><span class="sxs-lookup"><span data-stu-id="eef63-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="eef63-121">Der Generatortyp definiert die Vorgänge, die für den Ausdruck für die Berechnung verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="eef63-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="eef63-122">Finden Sie unter [erstellen einen neuen Typ von Ausdruck für die Berechnung](computation-expressions.md#creating-a-new-type-of-computation-expression), erfahren, wie Sie einen Ausdruck für die benutzerdefinierte Berechnung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="eef63-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="eef63-123">Übersicht über die Syntax</span><span class="sxs-lookup"><span data-stu-id="eef63-123">Syntax overview</span></span>

<span data-ttu-id="eef63-124">Alle Berechnungsausdrücke aufweisen folgende Form:</span><span class="sxs-lookup"><span data-stu-id="eef63-124">All computation expressions have the following form:</span></span>

```
builder-expr { cexper }
```

<span data-ttu-id="eef63-125">in denen `builder-expr` ist der Name eines Builder-Typs, der den Ausdruck für die Berechnung, definiert und `cexper` ist der Ausdruckstext, der den Ausdruck für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="eef63-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="eef63-126">Z. B. `async` Ausdruckscode Berechnung kann wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="eef63-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="eef63-127">Es ist eine spezielle, zusätzliche-Syntax in einem Berechnungsausdruck verfügbar, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="eef63-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="eef63-128">Die folgenden Ausdruck Formulare sind mit Berechnungsausdrücken möglich:</span><span class="sxs-lookup"><span data-stu-id="eef63-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="eef63-129">Jedes dieser Schlüsselwörter und andere Standard F# Schlüsselwörter sind nur in einem Berechnungsausdruck verfügbar, wenn sie in den unterstützenden-Generator-Typ definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="eef63-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="eef63-130">Die einzige Ausnahme hierbei ist `match!`, dies ist selbst die Syntax-Zuckerguss für die Verwendung von `let!` gefolgt von einer Musterübereinstimmung auf dem Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="eef63-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="eef63-131">Der Generator kann ein Objekt, das spezielle Methoden definiert, die steuern, die Möglichkeit, die die Fragmente des Berechnungsausdrucks kombiniert werden. d. h. seine Methoden Berechnungsausdrucks Verhalten steuern.</span><span class="sxs-lookup"><span data-stu-id="eef63-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="eef63-132">Eine weitere Möglichkeit zum Beschreiben einer Zeichenfolgengenerator-Klasse ist zu sagen, dass Sie den Vorgang von vielen anpassen können F# erstellt werden, beispielsweise Schleifen und Bindungen.</span><span class="sxs-lookup"><span data-stu-id="eef63-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="eef63-133">Die `let!` -Schlüsselwort bindet das Ergebnis eines Aufrufs von einem anderen Berechnungsausdruck an einen Namen:</span><span class="sxs-lookup"><span data-stu-id="eef63-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="eef63-134">Wenn Sie den Aufruf von einem Berechnungsausdruck mit binden `let`, erhalten Sie nicht das Ergebnis des Berechnungsausdrucks.</span><span class="sxs-lookup"><span data-stu-id="eef63-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="eef63-135">Stattdessen wird gebunden den Wert des der *realisierten* aufrufen, um dieser Ausdruck für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="eef63-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="eef63-136">Verwendung `let!` zum Binden an das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="eef63-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="eef63-137">`let!` wird definiert, indem die `Bind(x, f)` Member für den Generatortyp.</span><span class="sxs-lookup"><span data-stu-id="eef63-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="eef63-138">Die `do!` -Schlüsselwort ist für einen Ausdruck für die Berechnung aufrufen, gibt eine `unit`-wie (von definiert die `Zero` Member für den Generator):</span><span class="sxs-lookup"><span data-stu-id="eef63-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="eef63-139">Für die [asynchrone Workflows](asynchronous-workflows.md), dieser Typ ist `Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="eef63-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="eef63-140">Der Typ ist wahrscheinlich für die anderen Berechnungsausdrücken `CExpType<unit>`.</span><span class="sxs-lookup"><span data-stu-id="eef63-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="eef63-141">`do!` wird definiert, indem die `Bind(x, f)` Member für den Generatortyp, in denen `f` erzeugt eine `unit`.</span><span class="sxs-lookup"><span data-stu-id="eef63-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="eef63-142">Die `yield` -Schlüsselwort ist für die Rückgabe eines Werts aus den Berechnungsausdruck, damit es als verwendet werden kann ein <xref:System.Collections.Generic.IEnumerable%601>:</span><span class="sxs-lookup"><span data-stu-id="eef63-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="eef63-143">Wie bei der [yield-Schlüsselwort in c#](../../csharp/language-reference/keywords/yield.md), jedes Element in den Ausdruck für die Berechnung wird zurückgegeben, zurück, wie sie durchlaufen wird.</span><span class="sxs-lookup"><span data-stu-id="eef63-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="eef63-144">`yield` wird definiert, indem die `Yield(x)` Member für den Generatortyp, in denen `x` ist das Element, um wieder zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eef63-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="eef63-145">Die `yield!` -Schlüsselwort ist für das eine Auflistung von Werten aus einem Berechnungsausdruck reduzieren:</span><span class="sxs-lookup"><span data-stu-id="eef63-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="eef63-146">Bei der Auswertung, bezeichnet der Ausdruck für die Berechnung von `yield!` werden haben die Elemente zurückgegeben, die Back-nacheinander, vereinfachen das Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="eef63-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="eef63-147">`yield!` wird definiert, indem die `YieldFrom(x)` Member für den Generatortyp, in denen `x` ist eine Auflistung von Werten.</span><span class="sxs-lookup"><span data-stu-id="eef63-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="eef63-148">Die `return` Schlüsselwort umschließt einen Wert in den Typ, des Berechnungsausdrucks entspricht.</span><span class="sxs-lookup"><span data-stu-id="eef63-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="eef63-149">Abgesehen von der von Berechnungsausdrücken mit `yield`, er wird verwendet, um "einen Ausdruck für die Berechnung abgeschlossen werden":</span><span class="sxs-lookup"><span data-stu-id="eef63-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="eef63-150">`return` wird definiert, indem die `Return(x)` Member für den Generatortyp, in denen `x` ist das Element zu umschließen.</span><span class="sxs-lookup"><span data-stu-id="eef63-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="eef63-151">Die `return!` Schlüsselwort erkennt, dass den Wert eines Ausdrucks für die Berechnung und dient als Wrapper für das Ergebnis in den Typ, des Berechnungsausdrucks entsprechen:</span><span class="sxs-lookup"><span data-stu-id="eef63-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="eef63-152">`return!` wird definiert, indem die `ReturnFrom(x)` Member für den Generatortyp, in denen `x` wird von einem anderen Berechnungsausdruck.</span><span class="sxs-lookup"><span data-stu-id="eef63-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="eef63-153">Ab F# 4.5, den `match!` Schlüsselwort ermöglicht Sie Inline einen Aufruf an eine andere Berechnung Ausdruck und das Muster abzugleichen, das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="eef63-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="eef63-154">Beim Aufrufen von eines Berechnungsausdrucks mit `match!`, sie werden feststellen, das Ergebnis des Aufrufs wie `let!`.</span><span class="sxs-lookup"><span data-stu-id="eef63-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="eef63-155">Dies wird häufig verwendet, wenn einen Berechnungsausdruck aufrufen, ist das Ergebnis einer [optional](options.md).</span><span class="sxs-lookup"><span data-stu-id="eef63-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="eef63-156">Integrierte Berechnungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="eef63-156">Built-in computation expressions</span></span>

<span data-ttu-id="eef63-157">Die F# drei integrierte Berechnungsausdrücke definiert: [Sequence Expressions](sequences.md), [asynchrone Workflows](asynchronous-workflows.md), und [-Abfrageausdrücken](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="eef63-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="eef63-158">Erstellen eine neue Art von Ausdruck für die Berechnung</span><span class="sxs-lookup"><span data-stu-id="eef63-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="eef63-159">Sie können die Merkmale der eigene Berechnungsausdrücke definieren, indem eine Generatorklasse erstellen und definieren bestimmte speziellen Methoden für die Klasse.</span><span class="sxs-lookup"><span data-stu-id="eef63-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="eef63-160">Die Zeichenfolgengenerator-Klasse kann optional die Methoden definieren, wie in der folgenden Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="eef63-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="eef63-161">Die folgende Tabelle beschreibt die Methoden, die in einer Workflow-Generator-Klasse verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="eef63-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="eef63-162">**Methode**</span><span class="sxs-lookup"><span data-stu-id="eef63-162">**Method**</span></span>|<span data-ttu-id="eef63-163">**Typische Signaturen**</span><span class="sxs-lookup"><span data-stu-id="eef63-163">**Typical signature(s)**</span></span>|<span data-ttu-id="eef63-164">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="eef63-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="eef63-165">Wird aufgerufen, für die `let!` und `do!` im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="eef63-166">Umschließt einen Ausdruck für die Berechnung als Funktion an.</span><span class="sxs-lookup"><span data-stu-id="eef63-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="eef63-167">Wird aufgerufen, für die `return` im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="eef63-168">Wird aufgerufen, für die `return!` im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="eef63-169">`M<'T> -> M<'T>` oder</span><span class="sxs-lookup"><span data-stu-id="eef63-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="eef63-170">Führt einen Ausdruck für die Berechnung an.</span><span class="sxs-lookup"><span data-stu-id="eef63-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="eef63-171">`M<'T> * M<'T> -> M<'T>` oder</span><span class="sxs-lookup"><span data-stu-id="eef63-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="eef63-172">Wird aufgerufen, für die Sequenzierung im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="eef63-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` oder</span><span class="sxs-lookup"><span data-stu-id="eef63-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="eef63-174">Wird aufgerufen, für die `for...do` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="eef63-175">Wird aufgerufen, für die `try...finally` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="eef63-176">Wird aufgerufen, für die `try...with` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'U :> IDisposable`|<span data-ttu-id="eef63-177">Wird aufgerufen, für die `use` Bindungen in Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="eef63-178">Wird aufgerufen, für die `while...do` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="eef63-179">Wird aufgerufen, für die `yield` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="eef63-180">Wird aufgerufen, für die `yield!` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="eef63-181">Wird aufgerufen, für leere `else` branches `if...then` Ausdrücke im Berechnungsausdrücke.</span><span class="sxs-lookup"><span data-stu-id="eef63-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|

<span data-ttu-id="eef63-182">Viele der Methoden in einem Zeichenfolgengenerator-Klasse verwenden und Zurückgeben einer `M<'T>` Konstrukt, in der Regel separat definierten Typ, der die Art der Berechnungen, die kombiniert werden, z. B. charakterisiert, `Async<'T>` für asynchrone Workflows und `Seq<'T>` für die Sequenz-Workflows.</span><span class="sxs-lookup"><span data-stu-id="eef63-182">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="eef63-183">Die Signaturen der folgenden Methoden ermöglichen ihnen kombiniert und mit untereinander geschachtelt werden sollen, damit der Workflow-Objekt, das von einem Konstrukt zurückgegebene zum nächsten übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="eef63-183">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="eef63-184">Der Compiler, wenn es sich um einen Ausdruck für die Berechnung, analysiert konvertiert den Ausdruck in eine Reihe von Aufrufe geschachtelter Funktionen mithilfe von Methoden in der obigen Tabelle und der Code in den Ausdruck für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="eef63-184">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="eef63-185">Der geschachtelte Ausdruck ist im folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="eef63-185">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="eef63-186">Im obigen Code, die Aufrufe an `Run` und `Delay` werden ausgelassen, wenn sie nicht in der Berechnung Ausdrucks-Generator-Klasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="eef63-186">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="eef63-187">Der Text des Berechnungsausdrucks, hier bezeichnet als `{| cexpr |}`, durch die Übersetzungen, die in der folgenden Tabelle beschrieben in Aufrufe, die im Zusammenhang mit den Methoden der Builder-Klasse übersetzt.</span><span class="sxs-lookup"><span data-stu-id="eef63-187">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="eef63-188">Der Ausdruck für die Berechnung `{| cexpr |}` wird definierten rekursiv nach diese Übersetzungen, in denen `expr` ist ein F# Ausdruck und `cexpr` ist ein Ausdruck für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="eef63-188">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="eef63-189">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="eef63-189">Expression</span></span>|<span data-ttu-id="eef63-190">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="eef63-190">Translation</span></span>|
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

<span data-ttu-id="eef63-191">In der vorherigen Tabelle `other-expr` wird beschrieben, einen Ausdruck, der andernfalls nicht in der Tabelle aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="eef63-191">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="eef63-192">Eine Zeichenfolgengenerator-Klasse muss nicht alle Methoden zu implementieren und unterstützen alle die Übersetzungen, die in der vorherigen Tabelle aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="eef63-192">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="eef63-193">Diese Konstrukte, die nicht implementiert werden, sind nicht verfügbar ist, im Berechnungsausdrücke dieses Typs.</span><span class="sxs-lookup"><span data-stu-id="eef63-193">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="eef63-194">Angenommen, Sie nicht möchten, zur Unterstützung der `use` -Schlüsselwort in Berechnungsausdrücken, können Sie die Definition der weglassen `Use` in Ihre Zeichenfolgengenerator-Klasse.</span><span class="sxs-lookup"><span data-stu-id="eef63-194">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="eef63-195">Das folgende Codebeispiel zeigt einen Ausdruck für die Berechnung, der eine Berechnung kapselt, eine Reihe von Schritten, die sein können nur einem Schritt zu einem Zeitpunkt ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="eef63-195">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="eef63-196">Eine Unterscheidungs-union-Typs `OkOrException`, den Fehlerstatus des Ausdrucks codiert, wie bisher ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="eef63-196">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="eef63-197">Dieser Code zeigt einige typische Muster, die Sie in Ihrer Berechnungsausdrücken, z. B. Codebausteine Implementierung einiger der-Generator-Methoden verwenden können.</span><span class="sxs-lookup"><span data-stu-id="eef63-197">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="eef63-198">Ein Ausdruck für die Berechnung hat einen zugrunde liegenden Typ, der der Ausdruck zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="eef63-198">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="eef63-199">Der zugrunde liegende Typ kann eine berechnete Ergebnis oder eine verzögerte Berechnung, die ausgeführt werden kann oder darstellen kann es eine Möglichkeit zum iterieren durch eine Art von Auflistung bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="eef63-199">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="eef63-200">Im vorherigen Beispiel wurde der zugrunde liegende Typ **schließlich**.</span><span class="sxs-lookup"><span data-stu-id="eef63-200">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="eef63-201">Für einen Sequenzausdruck der zugrunde liegenden Typ ist <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eef63-201">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eef63-202">Bei einem Abfrageausdruck, der zugrunde liegende Typ ist <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="eef63-202">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="eef63-203">Ist ein asynchroner Workflow, der zugrunde liegenden Typ [ `Async` ](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="eef63-203">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="eef63-204">Die `Async` Objekt darstellt, die Arbeit ausgeführt werden, um das Ergebnis zu berechnen.</span><span class="sxs-lookup"><span data-stu-id="eef63-204">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="eef63-205">Rufen Sie z. B. [ `Async.RunSynchronously` ](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) führen eine Berechnung, und geben das Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="eef63-205">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="eef63-206">Benutzerdefinierte Vorgänge</span><span class="sxs-lookup"><span data-stu-id="eef63-206">Custom Operations</span></span>

<span data-ttu-id="eef63-207">Sie können einen Vorgang auf einen Ausdruck für die Berechnung definieren und verwenden einen Vorgang als einen Operator in einem Ausdruck für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="eef63-207">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="eef63-208">Beispielsweise können Sie einen Abfrageoperator in einem Abfrageausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="eef63-208">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="eef63-209">Wenn Sie einen Vorgang definieren, müssen Sie die "yield" definieren und für Methoden in den Ausdruck für die Berechnung.</span><span class="sxs-lookup"><span data-stu-id="eef63-209">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="eef63-210">Um einen Vorgang zu definieren, fügen Sie ihn in eine Builder-Klasse für den Ausdruck für die Berechnung aus, und wenden Sie dann die [ `CustomOperationAttribute` ](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span><span class="sxs-lookup"><span data-stu-id="eef63-210">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="eef63-211">Dieses Attribut akzeptiert eine Zeichenfolge als Argument, das heißt, die in einem benutzerdefinierten Vorgang verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eef63-211">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="eef63-212">Dieser Name wird in den Bereich am Anfang der öffnenden geschweiften Klammer des Berechnungsausdrucks.</span><span class="sxs-lookup"><span data-stu-id="eef63-212">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="eef63-213">Aus diesem Grund sollte nicht Sie Bezeichner mit den gleichen Namen wie einen Vorgang in diesem Block verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="eef63-213">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="eef63-214">Vermeiden Sie z. B. wie z. B. die Verwendung von Bezeichnern `all` oder `last` in Abfrageausdrücken.</span><span class="sxs-lookup"><span data-stu-id="eef63-214">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="eef63-215">Erweitern Sie vorhandene Generatoren mit neuen benutzerdefinierten-Vorgänge</span><span class="sxs-lookup"><span data-stu-id="eef63-215">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="eef63-216">Wenn Sie bereits über ein Zeichenfolgengenerator-Klasse verfügen, können benutzerdefinierte Vorgänge außerhalb dieser Zeichenfolgengenerator-Klasse aus erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="eef63-216">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="eef63-217">Erweiterungen müssen in Modulen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="eef63-217">Extensions must be declared in modules.</span></span> <span data-ttu-id="eef63-218">Namespaces können nicht enthalten, Erweiterungsmember außer in der gleichen Datei und der gleichen Namespace-Deklaration-Gruppe, in denen der Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="eef63-218">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="eef63-219">Das folgende Beispiel zeigt die Erweiterung des bestehenden `Microsoft.FSharp.Linq.QueryBuilder` Klasse.</span><span class="sxs-lookup"><span data-stu-id="eef63-219">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="eef63-220">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eef63-220">See also</span></span>

- [<span data-ttu-id="eef63-221">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="eef63-221">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="eef63-222">Asynchrone Workflows</span><span class="sxs-lookup"><span data-stu-id="eef63-222">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="eef63-223">Sequenzen</span><span class="sxs-lookup"><span data-stu-id="eef63-223">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="eef63-224">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="eef63-224">Query Expressions</span></span>](query-expressions.md)