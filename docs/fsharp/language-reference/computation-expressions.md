---
title: Berechnungsausdrücke
description: Erfahren Sie, wie Sie eine bequeme Syntax zum Schreiben von F# Berechnungen in erstellen, die mithilfe von Ablaufsteuerungskonstrukten und Bindungen sequenziert und kombiniert werden können.
ms.date: 03/15/2019
ms.openlocfilehash: 2f0eb7686378766f6b379f0401589490f01a1963
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424744"
---
# <a name="computation-expressions"></a><span data-ttu-id="64b6d-103">Berechnungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="64b6d-103">Computation Expressions</span></span>

<span data-ttu-id="64b6d-104">Berechnungs Ausdrücke in F# bieten eine bequeme Syntax zum Schreiben von Berechnungen, die mithilfe von Ablaufsteuerungskonstrukten und Bindungen sequenziert und kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="64b6d-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="64b6d-105">Abhängig von der Art des Berechnungs Ausdrucks können Sie sich als Möglichkeit vorstellen, Monads, Monoids, Monad-Transformatoren und Anwendungs Funktoren auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="64b6d-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="64b6d-106">Im Gegensatz zu anderen Sprachen (z. b. *do-Notation* in Haskell) sind Sie jedoch nicht an eine einzelne Abstraktion gebunden, und Sie verlassen sich nicht auf Makros oder andere Formen der Metaprogrammierung, um eine bequeme und kontextabhängige Syntax zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="64b6d-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="64b6d-107">Overview</span></span>

<span data-ttu-id="64b6d-108">Berechnungen können viele Formen annehmen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-108">Computations can take many forms.</span></span> <span data-ttu-id="64b6d-109">Die häufigste Form der Berechnung ist die Ausführung mit nur einem Thread, die leicht verständlich und geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="64b6d-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="64b6d-110">Allerdings sind nicht alle Berechnungs Formen so einfach wie die Ausführung mit einem Thread.</span><span class="sxs-lookup"><span data-stu-id="64b6d-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="64b6d-111">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="64b6d-111">Some examples include:</span></span>

- <span data-ttu-id="64b6d-112">Nicht deterministische Berechnungen</span><span class="sxs-lookup"><span data-stu-id="64b6d-112">Non-deterministic computations</span></span>
- <span data-ttu-id="64b6d-113">Asynchrone Berechnungen</span><span class="sxs-lookup"><span data-stu-id="64b6d-113">Asynchronous computations</span></span>
- <span data-ttu-id="64b6d-114">Effektive Berechnungen</span><span class="sxs-lookup"><span data-stu-id="64b6d-114">Effectful computations</span></span>
- <span data-ttu-id="64b6d-115">Generative Berechnungen</span><span class="sxs-lookup"><span data-stu-id="64b6d-115">Generative computations</span></span>

<span data-ttu-id="64b6d-116">Im Allgemeinen gibt es *kontextabhängige* Berechnungen, die Sie in bestimmten Teilen einer Anwendung ausführen müssen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="64b6d-117">Das Schreiben von Kontext sensiblem Code kann eine Herausforderung darstellen, da es einfach ist, Berechnungen außerhalb eines bestimmten Kontexts ohne Abstraktionen zu "vermeiden, um dies zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="64b6d-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="64b6d-118">Diese Abstraktionen sind oftmals schwierig zu schreiben, da es sich F# hierbei um eine generalisierte Methode handelt, die als **Berechnungs Ausdrücke**bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="64b6d-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="64b6d-119">Berechnungs Ausdrücke bieten ein einheitliches Syntax-und Abstraktions Modell zum Codieren kontextbezogener Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="64b6d-120">Jeder Berechnungs Ausdruck wird durch einen *Builder* -Typ unterstützt.</span><span class="sxs-lookup"><span data-stu-id="64b6d-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="64b6d-121">Der Builder-Typ definiert die Vorgänge, die für den Berechnungs Ausdruck verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="64b6d-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="64b6d-122">Weitere Informationen zum Erstellen eines benutzerdefinierten Berechnungs Ausdrucks finden Sie unter [Erstellen eines neuen Berechnungs Typs](computation-expressions.md#creating-a-new-type-of-computation-expression).</span><span class="sxs-lookup"><span data-stu-id="64b6d-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="64b6d-123">Syntax Übersicht</span><span class="sxs-lookup"><span data-stu-id="64b6d-123">Syntax overview</span></span>

<span data-ttu-id="64b6d-124">Alle Berechnungs Ausdrücke weisen die folgende Form auf:</span><span class="sxs-lookup"><span data-stu-id="64b6d-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="64b6d-125">Dabei ist `builder-expr` der Name eines Generator Typs, der den Berechnungs Ausdruck definiert, und `cexper` der Ausdrucks Text des Berechnungs Ausdrucks ist.</span><span class="sxs-lookup"><span data-stu-id="64b6d-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="64b6d-126">Beispielsweise kann `async` Berechnungs Ausdrucks Code wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="64b6d-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="64b6d-127">Es gibt eine spezielle, zusätzliche Syntax, die in einem Berechnungs Ausdruck verfügbar ist, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="64b6d-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="64b6d-128">Die folgenden Ausdrucksformen sind mit Berechnungs Ausdrücken möglich:</span><span class="sxs-lookup"><span data-stu-id="64b6d-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="64b6d-129">Jedes dieser Schlüsselwörter und andere Standard F# Schlüsselwörter sind nur in einem Berechnungs Ausdruck verfügbar, wenn Sie im Unterstützungs Generator-Typ definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="64b6d-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="64b6d-130">Die einzige Ausnahme ist `match!`, bei der es sich um den syntaktischen Text handelt, der für die Verwendung von `let!` gefolgt von einer Muster Übereinstimmung im Ergebnis vorliegt.</span><span class="sxs-lookup"><span data-stu-id="64b6d-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="64b6d-131">Der Builder-Typ ist ein Objekt, das spezielle Methoden definiert, die bestimmen, wie die Fragmente des Berechnungs Ausdrucks kombiniert werden. Das heißt, seine Methoden steuern, wie sich der Berechnungs Ausdruck verhält.</span><span class="sxs-lookup"><span data-stu-id="64b6d-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="64b6d-132">Eine andere Möglichkeit, eine Builder-Klasse zu beschreiben, besteht darin zu sagen, dass Sie die Ausführung F# vieler Konstrukte, wie z. b. Schleifen und Bindungen, anpassen können.</span><span class="sxs-lookup"><span data-stu-id="64b6d-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="64b6d-133">Das `let!`-Schlüsselwort bindet das Ergebnis eines Aufrufens an einen anderen Berechnungs Ausdruck an einen Namen:</span><span class="sxs-lookup"><span data-stu-id="64b6d-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="64b6d-134">Wenn Sie den-Ausdruck an einen Berechnungs Ausdruck mit `let`binden, wird das Ergebnis des Berechnungs Ausdrucks nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="64b6d-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="64b6d-135">Stattdessen haben Sie den Wert des *nicht erkannten* Aufrufes an diesen Berechnungs Ausdruck gebunden.</span><span class="sxs-lookup"><span data-stu-id="64b6d-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="64b6d-136">Verwenden Sie `let!`, um das Ergebnis zu binden.</span><span class="sxs-lookup"><span data-stu-id="64b6d-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="64b6d-137">`let!` wird vom `Bind(x, f)`-Member für den Builder-Typ definiert.</span><span class="sxs-lookup"><span data-stu-id="64b6d-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="64b6d-138">Das `do!` Schlüsselwort dient zum Aufrufen eines Berechnungs Ausdrucks, der einen `unit`ähnlichen Typ zurückgibt (der vom `Zero`-Member auf dem Generator definiert wird):</span><span class="sxs-lookup"><span data-stu-id="64b6d-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="64b6d-139">Für den [Async-Workflow](asynchronous-workflows.md)ist dieser Typ `Async<unit>`.</span><span class="sxs-lookup"><span data-stu-id="64b6d-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="64b6d-140">Bei anderen Berechnungs Ausdrücken ist der Typ wahrscheinlich `CExpType<unit>`.</span><span class="sxs-lookup"><span data-stu-id="64b6d-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="64b6d-141">`do!` wird vom `Bind(x, f)`-Member für den Builder-Typ definiert, wobei `f` eine `unit`erzeugt.</span><span class="sxs-lookup"><span data-stu-id="64b6d-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="64b6d-142">Das `yield` Schlüsselwort dient zum Zurückgeben eines Werts aus dem Berechnungs Ausdruck, sodass er als <xref:System.Collections.Generic.IEnumerable%601>verwendet werden kann:</span><span class="sxs-lookup"><span data-stu-id="64b6d-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="64b6d-143">Ebenso wie das [Yield-Schlüssel C#Wort in ](../../csharp/language-reference/keywords/yield.md)wird jedes Element im Berechnungs Ausdruck beim Durchlaufen zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="64b6d-143">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="64b6d-144">`yield` wird vom `Yield(x)`-Element für den Builder-Typ definiert, wobei `x` das Element ist, das zurückzugeben ist.</span><span class="sxs-lookup"><span data-stu-id="64b6d-144">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="64b6d-145">Das `yield!` Schlüsselwort dient zum Vereinfachen einer Auflistung von Werten aus einem Berechnungs Ausdruck:</span><span class="sxs-lookup"><span data-stu-id="64b6d-145">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="64b6d-146">Wenn das Ergebnis ausgewertet wird, werden die Elemente des von `yield!` aufgerufenen Berechnungs Ausdrucks nacheinander zurückgegeben und das Ergebnis vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="64b6d-146">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="64b6d-147">`yield!` wird vom `YieldFrom(x)`-Member für den Builder-Typ definiert, wobei `x` eine Auflistung von Werten ist.</span><span class="sxs-lookup"><span data-stu-id="64b6d-147">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

### `return`

<span data-ttu-id="64b6d-148">Das `return`-Schlüsselwort umschließt einen Wert in dem Typ, der dem Berechnungs Ausdruck entspricht.</span><span class="sxs-lookup"><span data-stu-id="64b6d-148">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="64b6d-149">Abgesehen von Berechnungs Ausdrücken, die `yield`verwenden, wird es verwendet, um einen Berechnungs Ausdruck zu vervollständigen:</span><span class="sxs-lookup"><span data-stu-id="64b6d-149">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="64b6d-150">`return` wird vom `Return(x)`-Member für den Builder-Typ definiert, wobei `x` das zu Umbruch Ende Element ist.</span><span class="sxs-lookup"><span data-stu-id="64b6d-150">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="64b6d-151">Das `return!`-Schlüsselwort erkennt den Wert eines Berechnungs Ausdrucks und umschließt das Ergebnis in den Typ, der dem Berechnungs Ausdruck entspricht:</span><span class="sxs-lookup"><span data-stu-id="64b6d-151">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="64b6d-152">`return!` wird vom `ReturnFrom(x)`-Member für den Builder-Typ definiert, wobei `x` ein weiterer Berechnungs Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="64b6d-152">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="64b6d-153">Ab 4,5 F# können Sie mit dem`match!`-Schlüsselwort einen aufzurufenden Berechnungs Ausdruck in eine Inline-und Muster Übereinstimmung für das Ergebnis überführen:</span><span class="sxs-lookup"><span data-stu-id="64b6d-153">Starting with F# 4.5, the `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="64b6d-154">Wenn Sie einen Berechnungs Ausdruck mit `match!`aufrufen, wird das Ergebnis des Aufrufs wie `let!`erkannt.</span><span class="sxs-lookup"><span data-stu-id="64b6d-154">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="64b6d-155">Dies wird häufig beim Aufrufen eines Berechnungs Ausdrucks verwendet, bei dem das Ergebnis [optional](options.md)ist.</span><span class="sxs-lookup"><span data-stu-id="64b6d-155">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="64b6d-156">Integrierte Berechnungs Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="64b6d-156">Built-in computation expressions</span></span>

<span data-ttu-id="64b6d-157">Die F# Core-Bibliothek definiert drei integrierte Berechnungs Ausdrücke: [Sequenz Ausdrücke](sequences.md), [asynchrone Workflows](asynchronous-workflows.md)und [Abfrage Ausdrücke](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="64b6d-157">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="64b6d-158">Erstellen eines neuen Typs des Berechnungs Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="64b6d-158">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="64b6d-159">Sie können die Merkmale ihrer eigenen Berechnungs Ausdrücke definieren, indem Sie eine Builder-Klasse erstellen und bestimmte spezielle Methoden für die Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="64b6d-159">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="64b6d-160">Die Builder-Klasse kann optional die Methoden wie in der folgenden Tabelle aufgeführt definieren.</span><span class="sxs-lookup"><span data-stu-id="64b6d-160">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="64b6d-161">In der folgenden Tabelle werden die Methoden beschrieben, die in einer Workflow Generator-Klasse verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="64b6d-161">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="64b6d-162">**Methode**</span><span class="sxs-lookup"><span data-stu-id="64b6d-162">**Method**</span></span>|<span data-ttu-id="64b6d-163">**Typische Signatur (en)**</span><span class="sxs-lookup"><span data-stu-id="64b6d-163">**Typical signature(s)**</span></span>|<span data-ttu-id="64b6d-164">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="64b6d-164">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="64b6d-165">Wird für `let!` und `do!` in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-165">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="64b6d-166">Umschließt einen Berechnungs Ausdruck als Funktion.</span><span class="sxs-lookup"><span data-stu-id="64b6d-166">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="64b6d-167">Wird für `return` in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-167">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="64b6d-168">Wird für `return!` in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-168">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="64b6d-169">`M<'T> -> M<'T>` oder</span><span class="sxs-lookup"><span data-stu-id="64b6d-169">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="64b6d-170">Führt einen Berechnungs Ausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="64b6d-170">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="64b6d-171">`M<'T> * M<'T> -> M<'T>` oder</span><span class="sxs-lookup"><span data-stu-id="64b6d-171">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="64b6d-172">Wird für die Sequenzierung in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-172">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="64b6d-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` oder</span><span class="sxs-lookup"><span data-stu-id="64b6d-173">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="64b6d-174">Wird für `for...do` Ausdrücke in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-174">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="64b6d-175">Wird für `try...finally` Ausdrücke in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-175">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="64b6d-176">Wird für `try...with` Ausdrücke in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-176">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="64b6d-177">Wird für `use` Bindungen in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-177">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="64b6d-178">Wird für `while...do` Ausdrücke in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-178">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="64b6d-179">Wird für `yield` Ausdrücke in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-179">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="64b6d-180">Wird für `yield!` Ausdrücke in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-180">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="64b6d-181">Wird für leere `else` branches von `if...then` Ausdrücken in Berechnungs Ausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-181">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="64b6d-182">Gibt an, dass der Berechnungs Ausdruck als Anführungszeichen an den `Run` Member übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="64b6d-182">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="64b6d-183">Dabei werden alle Instanzen einer Berechnung in ein Anführungszeichen übersetzt.</span><span class="sxs-lookup"><span data-stu-id="64b6d-183">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="64b6d-184">Viele der Methoden in einer Generator-Klasse verwenden und geben ein `M<'T>` Konstrukt zurück. Hierbei handelt es sich in der Regel um einen separat definierten Typ, der die Art der zu kombinierenden Berechnungen kennzeichnet, z. b. `Async<'T>` für asynchrone Workflows und `Seq<'T>` für die Sequenz. Workflows.</span><span class="sxs-lookup"><span data-stu-id="64b6d-184">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="64b6d-185">Mit den Signaturen dieser Methoden können Sie kombiniert und miteinander verknüpft werden, sodass das von einem Konstrukt zurückgegebene Workflow Objekt an das nächste weitergegeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="64b6d-185">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="64b6d-186">Wenn der Compiler einen Berechnungs Ausdruck analysiert, konvertiert er den Ausdruck in eine Reihe von geschalbten Funktionsaufrufen, indem er die Methoden in der vorangehenden Tabelle und den Code im Berechnungs Ausdruck verwendet.</span><span class="sxs-lookup"><span data-stu-id="64b6d-186">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="64b6d-187">Der-Ausdruck hat die folgende Form:</span><span class="sxs-lookup"><span data-stu-id="64b6d-187">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="64b6d-188">Im obigen Code werden die Aufrufe von `Run` und `Delay` ausgelassen, wenn Sie in der Berechnungs Ausdrucks-Generator-Klasse nicht definiert sind.</span><span class="sxs-lookup"><span data-stu-id="64b6d-188">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="64b6d-189">Der Text des Berechnungs Ausdrucks, der hier als `{| cexpr |}`bezeichnet wird, wird in Aufrufe übersetzt, die die Methoden der Generator-Klasse durch die in der folgenden Tabelle beschriebenen Übersetzungen einschließen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-189">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="64b6d-190">Der Berechnungs Ausdrucks `{| cexpr |}` wird rekursiv gemäß diesen Übersetzungen definiert, wobei `expr` F# ein Ausdruck und`cexpr`ein Berechnungs Ausdruck ist.</span><span class="sxs-lookup"><span data-stu-id="64b6d-190">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="64b6d-191">expression</span><span class="sxs-lookup"><span data-stu-id="64b6d-191">Expression</span></span>|<span data-ttu-id="64b6d-192">Übersetzung</span><span class="sxs-lookup"><span data-stu-id="64b6d-192">Translation</span></span>|
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
|<code>{ if expr then cexpr0 &#124;}</code>|<code>if expr then { cexpr0 } else binder.Zero()</code>|
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

<span data-ttu-id="64b6d-193">In der vorherigen Tabelle wird `other-expr` einen Ausdruck beschreiben, der in der Tabelle nicht anderweitig aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="64b6d-193">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="64b6d-194">Eine Builder-Klasse muss nicht alle Methoden implementieren und alle in der vorherigen Tabelle aufgeführten Übersetzungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-194">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="64b6d-195">Diese Konstrukte, die nicht implementiert werden, sind in Berechnungs Ausdrücken dieses Typs nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="64b6d-195">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="64b6d-196">Wenn Sie z. b. das `use`-Schlüsselwort in ihren Berechnungs Ausdrücken nicht unterstützen möchten, können Sie die Definition der `Use` in ihrer Builder-Klasse weglassen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-196">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="64b6d-197">Das folgende Codebeispiel zeigt einen Berechnungs Ausdruck, der eine Berechnung als eine Reihe von Schritten kapselt, die jeweils nacheinander ausgewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="64b6d-197">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="64b6d-198">Ein Unterscheidungs-Union-Typ, der `OkOrException`, codiert den Fehlerzustand des Ausdrucks, der bisher ausgewertet wurde.</span><span class="sxs-lookup"><span data-stu-id="64b6d-198">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="64b6d-199">In diesem Code werden mehrere typische Muster veranschaulicht, die Sie in ihren Berechnungs Ausdrücken verwenden können, wie z. b. die Implementierung von Code Bausteinen einiger Generator-Methoden.</span><span class="sxs-lookup"><span data-stu-id="64b6d-199">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="64b6d-200">Ein Berechnungs Ausdruck verfügt über einen zugrunde liegenden Typ, der vom Ausdruck zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="64b6d-200">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="64b6d-201">Der zugrunde liegende Typ kann ein berechnetes Ergebnis oder eine verzögerte Berechnung darstellen, die durchgeführt werden kann, oder es kann eine Möglichkeit bieten, einen Auflistungstyp zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-201">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="64b6d-202">Im vorherigen Beispiel war der zugrunde liegende Typ **schließlich**.</span><span class="sxs-lookup"><span data-stu-id="64b6d-202">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="64b6d-203">Bei einem Sequenz Ausdruck ist der zugrunde liegende Typ <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="64b6d-203">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="64b6d-204">Bei einem Abfrage Ausdruck ist der zugrunde liegende Typ <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="64b6d-204">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="64b6d-205">Bei einem asynchronen Workflow ist der zugrunde liegende Typ [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span><span class="sxs-lookup"><span data-stu-id="64b6d-205">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="64b6d-206">Das `Async`-Objekt stellt die Arbeit dar, die zum Berechnen des Ergebnisses ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="64b6d-206">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="64b6d-207">Beispielsweise wird [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) aufgerufen, um eine Berechnung auszuführen und das Ergebnis zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="64b6d-207">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="64b6d-208">Benutzerdefinierte Vorgänge</span><span class="sxs-lookup"><span data-stu-id="64b6d-208">Custom Operations</span></span>

<span data-ttu-id="64b6d-209">Sie können einen benutzerdefinierten Vorgang für einen Berechnungs Ausdruck definieren und einen benutzerdefinierten Vorgang als Operator in einem Berechnungs Ausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="64b6d-209">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="64b6d-210">Beispielsweise können Sie einen Abfrage Operator in einen Abfrage Ausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="64b6d-210">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="64b6d-211">Wenn Sie einen benutzerdefinierten Vorgang definieren, müssen Sie die Yield-und for-Methoden im Berechnungs Ausdruck definieren.</span><span class="sxs-lookup"><span data-stu-id="64b6d-211">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="64b6d-212">Um einen benutzerdefinierten Vorgang zu definieren, fügen Sie ihn in eine Builder-Klasse für den Berechnungs Ausdruck ein, und wenden Sie dann die [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)an.</span><span class="sxs-lookup"><span data-stu-id="64b6d-212">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="64b6d-213">Dieses Attribut verwendet eine Zeichenfolge als Argument. Dies ist der Name, der in einem benutzerdefinierten Vorgang verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="64b6d-213">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="64b6d-214">Dieser Name tritt am Anfang der öffnenden geschweiften Klammer des Berechnungs Ausdrucks auf.</span><span class="sxs-lookup"><span data-stu-id="64b6d-214">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="64b6d-215">Daher sollten Sie keine Bezeichner verwenden, die denselben Namen wie ein benutzerdefinierter Vorgang in diesem Block haben.</span><span class="sxs-lookup"><span data-stu-id="64b6d-215">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="64b6d-216">Vermeiden Sie z. b. die Verwendung von bezeichlern, wie z. b. `all` oder `last` in Abfrage Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="64b6d-216">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="64b6d-217">Erweitern vorhandener Generatoren mit neuen benutzerdefinierten Vorgängen</span><span class="sxs-lookup"><span data-stu-id="64b6d-217">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="64b6d-218">Wenn Sie bereits über eine Builder-Klasse verfügen, können die benutzerdefinierten Vorgänge von außerhalb dieser Builder-Klasse erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="64b6d-218">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="64b6d-219">Erweiterungen müssen in Modulen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="64b6d-219">Extensions must be declared in modules.</span></span> <span data-ttu-id="64b6d-220">Namespaces dürfen keine Erweiterungs Elemente enthalten, außer in derselben Datei und derselben Namespace-Deklarations Gruppe, in der der Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="64b6d-220">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="64b6d-221">Das folgende Beispiel zeigt die Erweiterung der vorhandenen `Microsoft.FSharp.Linq.QueryBuilder`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="64b6d-221">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member __.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="64b6d-222">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64b6d-222">See also</span></span>

- [<span data-ttu-id="64b6d-223">F#-Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="64b6d-223">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="64b6d-224">Asynchrone Workflows</span><span class="sxs-lookup"><span data-stu-id="64b6d-224">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="64b6d-225">Sequenzen</span><span class="sxs-lookup"><span data-stu-id="64b6d-225">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="64b6d-226">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="64b6d-226">Query Expressions</span></span>](query-expressions.md)
