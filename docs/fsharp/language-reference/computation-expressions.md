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
# <a name="computation-expressions"></a><span data-ttu-id="ac056-103">Berechnungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="ac056-103">Computation Expressions</span></span>

<span data-ttu-id="ac056-104">Berechnungsausdrücke in F' bieten eine praktische Syntax zum Schreiben von Berechnungen, die mithilfe von Steuerungsflusskonstrukten und -bindungen sequenziert und kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="ac056-104">Computation expressions in F# provide a convenient syntax for writing computations that can be sequenced and combined using control flow constructs and bindings.</span></span> <span data-ttu-id="ac056-105">Je nach Art des Berechnungsausdrucks können sie als eine Möglichkeit betrachtet werden, Monaden, Monoide, Monadentransformatoren und applikative Funker auszudrücken.</span><span class="sxs-lookup"><span data-stu-id="ac056-105">Depending on the kind of computation expression, they can be thought of as a way to express monads, monoids, monad transformers, and applicative functors.</span></span> <span data-ttu-id="ac056-106">Im Gegensatz zu anderen Sprachen (z. B. *Do-Notation* in Haskell) sind sie jedoch nicht an eine einzelne Abstraktion gebunden und verlassen sich nicht auf Makros oder andere Formen der Metaprogrammierung, um eine bequeme und kontextsensitive Syntax zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="ac056-106">However, unlike other languages (such as *do-notation* in Haskell), they are not tied to a single abstraction, and do not rely on macros or other forms of metaprogramming to accomplish a convenient and context-sensitive syntax.</span></span>

## <a name="overview"></a><span data-ttu-id="ac056-107">Übersicht</span><span class="sxs-lookup"><span data-stu-id="ac056-107">Overview</span></span>

<span data-ttu-id="ac056-108">Berechnungen können viele Formen annehmen.</span><span class="sxs-lookup"><span data-stu-id="ac056-108">Computations can take many forms.</span></span> <span data-ttu-id="ac056-109">Die häufigste Form der Berechnung ist die Ausführung mit einem Thread, die leicht zu verstehen und zu ändern ist.</span><span class="sxs-lookup"><span data-stu-id="ac056-109">The most common form of computation is single-threaded execution, which is easy to understand and modify.</span></span> <span data-ttu-id="ac056-110">Allerdings sind nicht alle Formen der Berechnung so einfach wie die Ausführung mit einem Thread.</span><span class="sxs-lookup"><span data-stu-id="ac056-110">However, not all forms of computation are as straightforward as single-threaded execution.</span></span> <span data-ttu-id="ac056-111">Beispiele hierfür sind:</span><span class="sxs-lookup"><span data-stu-id="ac056-111">Some examples include:</span></span>

- <span data-ttu-id="ac056-112">Nicht deterministische Berechnungen</span><span class="sxs-lookup"><span data-stu-id="ac056-112">Non-deterministic computations</span></span>
- <span data-ttu-id="ac056-113">Asynchrone Berechnungen</span><span class="sxs-lookup"><span data-stu-id="ac056-113">Asynchronous computations</span></span>
- <span data-ttu-id="ac056-114">Effektive Berechnungen</span><span class="sxs-lookup"><span data-stu-id="ac056-114">Effectful computations</span></span>
- <span data-ttu-id="ac056-115">Generative Berechnungen</span><span class="sxs-lookup"><span data-stu-id="ac056-115">Generative computations</span></span>

<span data-ttu-id="ac056-116">Im Allgemeinen gibt es *kontextsensitive* Berechnungen, die Sie in bestimmten Teilen einer Anwendung durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="ac056-116">More generally, there are *context-sensitive* computations that you must perform in certain parts of an application.</span></span> <span data-ttu-id="ac056-117">Das Schreiben von kontextsensitivem Code kann eine Herausforderung sein, da es einfach ist, Berechnungen außerhalb eines bestimmten Kontexts ohne Abstraktionen zu "lecken", um Sie daran zu hindern.</span><span class="sxs-lookup"><span data-stu-id="ac056-117">Writing context-sensitive code can be challenging, as it is easy to "leak" computations outside of a given context without abstractions to prevent you from doing so.</span></span> <span data-ttu-id="ac056-118">Diese Abstraktionen sind oft eine Herausforderung, um selbst zu schreiben, weshalb f. eine verallgemeinerte Möglichkeit hat, so genannte **Berechnungsausdrücke**zu tun.</span><span class="sxs-lookup"><span data-stu-id="ac056-118">These abstractions are often challenging to write by yourself, which is why F# has a generalized way to do so called **computation expressions**.</span></span>

<span data-ttu-id="ac056-119">Berechnungsausdrücke bieten ein einheitliches Syntax- und Abstraktionsmodell für die Codierung kontextsensitiver Berechnungen.</span><span class="sxs-lookup"><span data-stu-id="ac056-119">Computation expressions offer a uniform syntax and abstraction model for encoding context-sensitive computations.</span></span>

<span data-ttu-id="ac056-120">Jeder Berechnungsausdruck wird von einem *Buildertyp* unterstützt.</span><span class="sxs-lookup"><span data-stu-id="ac056-120">Every computation expression is backed by a *builder* type.</span></span> <span data-ttu-id="ac056-121">Der Buildertyp definiert die Vorgänge, die für den Berechnungsausdruck verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="ac056-121">The builder type defines the operations that are available for the computation expression.</span></span> <span data-ttu-id="ac056-122">Weitere Informationen finden Sie unter [Erstellen eines neuen Berechnungsausdrucks](computation-expressions.md#creating-a-new-type-of-computation-expression), der zeigt, wie ein benutzerdefinierter Berechnungsausdruck erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ac056-122">See [Creating a New Type of Computation Expression](computation-expressions.md#creating-a-new-type-of-computation-expression), which shows how to create a custom computation expression.</span></span>

### <a name="syntax-overview"></a><span data-ttu-id="ac056-123">Syntaxübersicht</span><span class="sxs-lookup"><span data-stu-id="ac056-123">Syntax overview</span></span>

<span data-ttu-id="ac056-124">Alle Berechnungsausdrücke haben die folgende Form:</span><span class="sxs-lookup"><span data-stu-id="ac056-124">All computation expressions have the following form:</span></span>

```fsharp
builder-expr { cexper }
```

<span data-ttu-id="ac056-125">Wobei `builder-expr` der Name eines Builder-Typs ist, `cexper` der den Berechnungsausdruck definiert, und der Ausdruckskörper des Berechnungsausdrucks ist.</span><span class="sxs-lookup"><span data-stu-id="ac056-125">where `builder-expr` is the name of a builder type that defines the computation expression, and `cexper` is the expression body of the computation expression.</span></span> <span data-ttu-id="ac056-126">Der Berechnungsexpressionscode `async` kann z. B. wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="ac056-126">For example, `async` computation expression code can look like this:</span></span>

```fsharp
let fetchAndDownload url =
    async {
        let! data = downloadData url

        let processedData = processData data

        return processedData
    }
```

<span data-ttu-id="ac056-127">In einem Berechnungsausdruck ist eine spezielle, zusätzliche Syntax verfügbar, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="ac056-127">There is a special, additional syntax available within a computation expression, as shown in the previous example.</span></span> <span data-ttu-id="ac056-128">Die folgenden Ausdrucksformen sind mit Berechnungsausdrücken möglich:</span><span class="sxs-lookup"><span data-stu-id="ac056-128">The following expression forms are possible with computation expressions:</span></span>

```fsharp
expr { let! ... }
expr { do! ... }
expr { yield ... }
expr { yield! ... }
expr { return ... }
expr { return! ... }
expr { match! ... }
```

<span data-ttu-id="ac056-129">Jedes dieser Schlüsselwörter und andere Standardschlüsselwörter sind nur in einem Berechnungsausdruck verfügbar, wenn sie im Sicherungs-Generatortyp definiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ac056-129">Each of these keywords, and other standard F# keywords are only available in a computation expression if they have been defined in the backing builder type.</span></span> <span data-ttu-id="ac056-130">Die einzige Ausnahme `match!`ist , die selbst syntaktischer `let!` Zucker für die Verwendung von gefolgt von einem Muster Übereinstimmung auf das Ergebnis ist.</span><span class="sxs-lookup"><span data-stu-id="ac056-130">The only exception to this is `match!`, which is itself syntactic sugar for the use of `let!` followed by a pattern match on the result.</span></span>

<span data-ttu-id="ac056-131">Der Builder-Typ ist ein Objekt, das spezielle Methoden definiert, die die Art und Weise steuern, wie die Fragmente des Berechnungsausdrucks kombiniert werden. Das heißt, seine Methoden steuern, wie sich der Berechnungsausdruck verhält.</span><span class="sxs-lookup"><span data-stu-id="ac056-131">The builder type is an object that defines special methods that govern the way the fragments of the computation expression are combined; that is, its methods control how the computation expression behaves.</span></span> <span data-ttu-id="ac056-132">Eine andere Möglichkeit, eine Builder-Klasse zu beschreiben, besteht darin, zu sagen, dass Sie damit die Operation vieler F-Konstrukte anpassen können, z. B. Schleifen und Bindungen.</span><span class="sxs-lookup"><span data-stu-id="ac056-132">Another way to describe a builder class is to say that it enables you to customize the operation of many F# constructs, such as loops and bindings.</span></span>

### `let!`

<span data-ttu-id="ac056-133">Das `let!` Schlüsselwort bindet das Ergebnis eines Aufrufs an einen anderen Berechnungsausdruck an einen Namen:</span><span class="sxs-lookup"><span data-stu-id="ac056-133">The `let!` keyword binds the result of a call to another computation expression to a name:</span></span>

```fsharp
let doThingsAsync url =
    async {
        let! data = getDataAsync url
        ...
    }
```

<span data-ttu-id="ac056-134">Wenn Sie den Aufruf an `let`einen Berechnungsausdruck mit binden, erhalten Sie nicht das Ergebnis des Berechnungsausdrucks.</span><span class="sxs-lookup"><span data-stu-id="ac056-134">If you bind the call to a computation expression with `let`, you will not get the result of the computation expression.</span></span> <span data-ttu-id="ac056-135">Stattdessen haben Sie den Wert des *nicht realisierten* Aufrufs an diesen Berechnungsausdruck gebunden.</span><span class="sxs-lookup"><span data-stu-id="ac056-135">Instead, you will have bound the value of the *unrealized* call to that computation expression.</span></span> <span data-ttu-id="ac056-136">Verwenden `let!` Sie diese Datei, um an das Ergebnis zu binden.</span><span class="sxs-lookup"><span data-stu-id="ac056-136">Use `let!` to bind to the result.</span></span>

<span data-ttu-id="ac056-137">`let!`wird durch `Bind(x, f)` das Element im Buildertyp definiert.</span><span class="sxs-lookup"><span data-stu-id="ac056-137">`let!` is defined by the `Bind(x, f)` member on the builder type.</span></span>

### `do!`

<span data-ttu-id="ac056-138">Das `do!` Schlüsselwort dient zum Aufrufen `unit`eines Berechnungsausdrucks, `Zero` der einen -like-Typ zurückgibt (definiert durch den Member auf dem Builder):</span><span class="sxs-lookup"><span data-stu-id="ac056-138">The `do!` keyword is for calling a computation expression that returns a `unit`-like type (defined by the `Zero` member on the builder):</span></span>

```fsharp
let doThingsAsync data url =
    async {
        do! submitData data url
        ...
    }
```

<span data-ttu-id="ac056-139">Für den [async-Workflow](asynchronous-workflows.md) `Async<unit>`lautet dieser Typ .</span><span class="sxs-lookup"><span data-stu-id="ac056-139">For the [async workflow](asynchronous-workflows.md), this type is `Async<unit>`.</span></span> <span data-ttu-id="ac056-140">Bei anderen Berechnungsausdrücken ist `CExpType<unit>`der Typ wahrscheinlich .</span><span class="sxs-lookup"><span data-stu-id="ac056-140">For other computation expressions, the type is likely to be `CExpType<unit>`.</span></span>

<span data-ttu-id="ac056-141">`do!`wird durch `Bind(x, f)` das Element auf dem `f` Builder-Typ definiert, wobei eine erzeugt wird. `unit`</span><span class="sxs-lookup"><span data-stu-id="ac056-141">`do!` is defined by the `Bind(x, f)` member on the builder type, where `f` produces a `unit`.</span></span>

### `yield`

<span data-ttu-id="ac056-142">Das `yield` Schlüsselwort dient zum Zurückgeben eines Werts aus dem <xref:System.Collections.Generic.IEnumerable%601>Berechnungsausdruck, damit er als :</span><span class="sxs-lookup"><span data-stu-id="ac056-142">The `yield` keyword is for returning a value from the computation expression so that it can be consumed as an <xref:System.Collections.Generic.IEnumerable%601>:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 do
            yield i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="ac056-143">In den meisten Fällen kann es von Aufrufern weggelassen werden.</span><span class="sxs-lookup"><span data-stu-id="ac056-143">In most cases, it can be omitted by callers.</span></span> <span data-ttu-id="ac056-144">Der häufigste Weg, `yield` um zu `->` unterlassen ist mit dem Operator:</span><span class="sxs-lookup"><span data-stu-id="ac056-144">The most common way to omit `yield` is with the `->` operator:</span></span>

```fsharp
let squares =
    seq {
        for i in 1..10 -> i * i
    }

for sq in squares do
    printfn "%d" sq
```

<span data-ttu-id="ac056-145">Bei komplexeren Ausdrücken, die viele verschiedene Werte ergeben können, und möglicherweise bedingt, kann das Auslassen des Schlüsselworts:</span><span class="sxs-lookup"><span data-stu-id="ac056-145">For more complex expressions that might yield many different values, and perhaps conditionally, simply omitting the keyword can do:</span></span>

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

<span data-ttu-id="ac056-146">Wie beim [yield-Schlüsselwort in C-](../../csharp/language-reference/keywords/yield.md)wird jedes Element im Berechnungsausdruck zurückgegeben, wenn es iteriert wird.</span><span class="sxs-lookup"><span data-stu-id="ac056-146">As with the [yield keyword in C#](../../csharp/language-reference/keywords/yield.md), each element in the computation expression is yielded back as it is iterated.</span></span>

<span data-ttu-id="ac056-147">`yield`wird durch `Yield(x)` das Element im Builder-Typ definiert, wobei `x` das Element zurückgegeben werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac056-147">`yield` is defined by the `Yield(x)` member on the builder type, where `x` is the item to yield back.</span></span>

### `yield!`

<span data-ttu-id="ac056-148">Das `yield!` Schlüsselwort dient zum Abflachen einer Auflistung von Werten aus einem Berechnungsausdruck:</span><span class="sxs-lookup"><span data-stu-id="ac056-148">The `yield!` keyword is for flattening a collection of values from a computation expression:</span></span>

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

<span data-ttu-id="ac056-149">Bei der Auswertung wird `yield!` der von aufgerufene Berechnungsausdruck seine Elemente nacheinander zurückgeben und das Ergebnis verflachen.</span><span class="sxs-lookup"><span data-stu-id="ac056-149">When evaluated, the computation expression called by `yield!` will have its items yielded back one-by-one, flattening the result.</span></span>

<span data-ttu-id="ac056-150">`yield!`wird durch `YieldFrom(x)` den Member im Buildertyp definiert, wobei es sich `x` um eine Auflistung von Werten handelt.</span><span class="sxs-lookup"><span data-stu-id="ac056-150">`yield!` is defined by the `YieldFrom(x)` member on the builder type, where `x` is a collection of values.</span></span>

<span data-ttu-id="ac056-151">Im `yield` `yield!` Gegensatz zu muss explizit angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="ac056-151">Unlike `yield`, `yield!` must be explicitly specified.</span></span> <span data-ttu-id="ac056-152">Sein Verhalten ist in Berechnungsausdrücken nicht implizit.</span><span class="sxs-lookup"><span data-stu-id="ac056-152">Its behavior isn't implicit in computation expressions.</span></span>

### `return`

<span data-ttu-id="ac056-153">Das `return` Schlüsselwort umschließt einen Wert in dem Typ, der dem Berechnungsausdruck entspricht.</span><span class="sxs-lookup"><span data-stu-id="ac056-153">The `return` keyword wraps a value in the type corresponding to the computation expression.</span></span> <span data-ttu-id="ac056-154">Abgesehen von Berechnungsausdrücken, `yield`die verwendet werden, wird es verwendet, um einen Berechnungsausdruck zu "vervollständigen":</span><span class="sxs-lookup"><span data-stu-id="ac056-154">Aside from computation expressions using `yield`, it is used to "complete" a computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        let! data = fetch url
        return data
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="ac056-155">`return`wird durch `Return(x)` das Element im Buildertyp definiert, wobei `x` das zu umschließende Element ist.</span><span class="sxs-lookup"><span data-stu-id="ac056-155">`return` is defined by the `Return(x)` member on the builder type, where `x` is the item to wrap.</span></span>

### `return!`

<span data-ttu-id="ac056-156">Das `return!` Schlüsselwort erkennt den Wert eines Berechnungsausdrucks und umschließt den Typ, der dem Berechnungsausdruck entspricht:</span><span class="sxs-lookup"><span data-stu-id="ac056-156">The `return!` keyword realizes the value of a computation expression and wraps that result in the type corresponding to the computation expression:</span></span>

```fsharp
let req = // 'req' is of type is 'Async<data>'
    async {
        return! fetch url
    }

// 'result' is of type 'data'
let result = Async.RunSynchronously req
```

<span data-ttu-id="ac056-157">`return!`wird durch `ReturnFrom(x)` das Element im Buildertyp definiert, wobei `x` es sich um einen anderen Berechnungsausdruck handelt.</span><span class="sxs-lookup"><span data-stu-id="ac056-157">`return!` is defined by the `ReturnFrom(x)` member on the builder type, where `x` is another computation expression.</span></span>

### `match!`

<span data-ttu-id="ac056-158">Mit `match!` dem Schlüsselwort können Sie einen Aufruf eines anderen Berechnungsausdrucks und einer Musterübereinstimmung für das Ergebnis inline:</span><span class="sxs-lookup"><span data-stu-id="ac056-158">The `match!` keyword allows you to inline a call to another computation expression and pattern match on its result:</span></span>

```fsharp
let doThingsAsync url =
    async {
        match! callService url with
        | Some data -> ...
        | None -> ...
    }
```

<span data-ttu-id="ac056-159">Beim Aufrufen eines `match!`Berechnungsausdrucks mit wird das `let!`Ergebnis des Aufrufs wie realisiert.</span><span class="sxs-lookup"><span data-stu-id="ac056-159">When calling a computation expression with `match!`, it will realize the result of the call like `let!`.</span></span> <span data-ttu-id="ac056-160">Dies wird häufig beim Aufrufen eines Berechnungsausdrucks verwendet, bei dem das Ergebnis ein [optionaler](options.md)ist.</span><span class="sxs-lookup"><span data-stu-id="ac056-160">This is often used when calling a computation expression where the result is an [optional](options.md).</span></span>

## <a name="built-in-computation-expressions"></a><span data-ttu-id="ac056-161">Integrierte Berechnungsausdrücke</span><span class="sxs-lookup"><span data-stu-id="ac056-161">Built-in computation expressions</span></span>

<span data-ttu-id="ac056-162">Die Kernbibliothek von F- definiert drei integrierte Berechnungsausdrücke: [Sequenzausdrücke](sequences.md), [Asynchrone Workflows](asynchronous-workflows.md)und [Abfrageausdrücke](query-expressions.md).</span><span class="sxs-lookup"><span data-stu-id="ac056-162">The F# core library defines three built-in computation expressions: [Sequence Expressions](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Query Expressions](query-expressions.md).</span></span>

## <a name="creating-a-new-type-of-computation-expression"></a><span data-ttu-id="ac056-163">Erstellen eines neuen Berechnungsausdruckstyps</span><span class="sxs-lookup"><span data-stu-id="ac056-163">Creating a New Type of Computation Expression</span></span>

<span data-ttu-id="ac056-164">Sie können die Merkmale Ihrer eigenen Berechnungsausdrücke definieren, indem Sie eine Builder-Klasse erstellen und bestimmte spezielle Methoden für die Klasse definieren.</span><span class="sxs-lookup"><span data-stu-id="ac056-164">You can define the characteristics of your own computation expressions by creating a builder class and defining certain special methods on the class.</span></span> <span data-ttu-id="ac056-165">Die Builder-Klasse kann optional die in der folgenden Tabelle aufgeführten Methoden definieren.</span><span class="sxs-lookup"><span data-stu-id="ac056-165">The builder class can optionally define the methods as listed in the following table.</span></span>

<span data-ttu-id="ac056-166">In der folgenden Tabelle werden Methoden beschrieben, die in einer Workflow-Builderklasse verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ac056-166">The following table describes methods that can be used in a workflow builder class.</span></span>

|<span data-ttu-id="ac056-167">**Methode**</span><span class="sxs-lookup"><span data-stu-id="ac056-167">**Method**</span></span>|<span data-ttu-id="ac056-168">**Typische Signatur(n)**</span><span class="sxs-lookup"><span data-stu-id="ac056-168">**Typical signature(s)**</span></span>|<span data-ttu-id="ac056-169">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="ac056-169">**Description**</span></span>|
|----|----|----|
|`Bind`|`M<'T> * ('T -> M<'U>) -> M<'U>`|<span data-ttu-id="ac056-170">Aufgerufen `let!` für `do!` und in Berechnungsausdrücken.</span><span class="sxs-lookup"><span data-stu-id="ac056-170">Called for `let!` and `do!` in computation expressions.</span></span>|
|`Delay`|`(unit -> M<'T>) -> M<'T>`|<span data-ttu-id="ac056-171">Umschließt einen Berechnungsausdruck als Funktion.</span><span class="sxs-lookup"><span data-stu-id="ac056-171">Wraps a computation expression as a function.</span></span>|
|`Return`|`'T -> M<'T>`|<span data-ttu-id="ac056-172">In `return` Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-172">Called for `return` in computation expressions.</span></span>|
|`ReturnFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="ac056-173">In `return!` Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-173">Called for `return!` in computation expressions.</span></span>|
|`Run`|<span data-ttu-id="ac056-174">`M<'T> -> M<'T>` oder</span><span class="sxs-lookup"><span data-stu-id="ac056-174">`M<'T> -> M<'T>` or</span></span><br /><br />`M<'T> -> 'T`|<span data-ttu-id="ac056-175">Führt einen Berechnungsausdruck aus.</span><span class="sxs-lookup"><span data-stu-id="ac056-175">Executes a computation expression.</span></span>|
|`Combine`|<span data-ttu-id="ac056-176">`M<'T> * M<'T> -> M<'T>` oder</span><span class="sxs-lookup"><span data-stu-id="ac056-176">`M<'T> * M<'T> -> M<'T>` or</span></span><br /><br />`M<unit> * M<'T> -> M<'T>`|<span data-ttu-id="ac056-177">Wird zur Sequenzierung in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-177">Called for sequencing in computation expressions.</span></span>|
|`For`|<span data-ttu-id="ac056-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` oder</span><span class="sxs-lookup"><span data-stu-id="ac056-178">`seq<'T> * ('T -> M<'U>) -> M<'U>` or</span></span><br /><br />`seq<'T> * ('T -> M<'U>) -> seq<M<'U>>`|<span data-ttu-id="ac056-179">Wird `for...do` für Ausdrücke in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-179">Called for `for...do` expressions in computation expressions.</span></span>|
|`TryFinally`|`M<'T> * (unit -> unit) -> M<'T>`|<span data-ttu-id="ac056-180">Wird `try...finally` für Ausdrücke in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-180">Called for `try...finally` expressions in computation expressions.</span></span>|
|`TryWith`|`M<'T> * (exn -> M<'T>) -> M<'T>`|<span data-ttu-id="ac056-181">Wird `try...with` für Ausdrücke in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-181">Called for `try...with` expressions in computation expressions.</span></span>|
|`Using`|`'T * ('T -> M<'U>) -> M<'U> when 'T :> IDisposable`|<span data-ttu-id="ac056-182">Wird `use` für Bindungen in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-182">Called for `use` bindings in computation expressions.</span></span>|
|`While`|`(unit -> bool) * M<'T> -> M<'T>`|<span data-ttu-id="ac056-183">Wird `while...do` für Ausdrücke in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-183">Called for `while...do` expressions in computation expressions.</span></span>|
|`Yield`|`'T -> M<'T>`|<span data-ttu-id="ac056-184">Wird `yield` für Ausdrücke in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-184">Called for `yield` expressions in computation expressions.</span></span>|
|`YieldFrom`|`M<'T> -> M<'T>`|<span data-ttu-id="ac056-185">Wird `yield!` für Ausdrücke in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-185">Called for `yield!` expressions in computation expressions.</span></span>|
|`Zero`|`unit -> M<'T>`|<span data-ttu-id="ac056-186">Wird für `else` leere `if...then` Auszweigungen von Ausdrücken in Berechnungsausdrücken aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="ac056-186">Called for empty `else` branches of `if...then` expressions in computation expressions.</span></span>|
|`Quote`|`Quotations.Expr<'T> -> Quotations.Expr<'T>`|<span data-ttu-id="ac056-187">Gibt an, dass der `Run` Berechnungsausdruck als Zitat an das Element übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="ac056-187">Indicates that the computation expression is passed to the `Run` member as a quotation.</span></span> <span data-ttu-id="ac056-188">Es übersetzt alle Instanzen einer Berechnung in ein Zitat.</span><span class="sxs-lookup"><span data-stu-id="ac056-188">It translates all instances of a computation into a quotation.</span></span>|

<span data-ttu-id="ac056-189">Viele der Methoden in einer Builderklasse `M<'T>` verwenden und geben ein Konstrukt zurück, bei dem es sich in `Async<'T>` der Regel um `Seq<'T>` einen separat definierten Typ handelt, der die Art der Berechnungen charakterisiert, die kombiniert werden, z. B. für asynchrone Workflows und für Sequenzworkflows.</span><span class="sxs-lookup"><span data-stu-id="ac056-189">Many of the methods in a builder class use and return an `M<'T>` construct, which is typically a separately defined type that characterizes the kind of computations being combined, for example, `Async<'T>` for asynchronous workflows and `Seq<'T>` for sequence workflows.</span></span> <span data-ttu-id="ac056-190">Die Signaturen dieser Methoden ermöglichen es, sie miteinander zu kombinieren und zu verschachteln, sodass das von einem Konstrukt zurückgegebene Workflowobjekt an das nächste übergeben werden kann.</span><span class="sxs-lookup"><span data-stu-id="ac056-190">The signatures of these methods enable them to be combined and nested with each other, so that the workflow object returned from one construct can be passed to the next.</span></span> <span data-ttu-id="ac056-191">Wenn der Compiler einen Berechnungsausdruck analysiert, konvertiert er den Ausdruck in eine Reihe von geschachtelten Funktionsaufrufen, indem er die Methoden in der vorherigen Tabelle und den Code im Berechnungsausdruck verwendet.</span><span class="sxs-lookup"><span data-stu-id="ac056-191">The compiler, when it parses a computation expression, converts the expression into a series of nested function calls by using the methods in the preceding table and the code in the computation expression.</span></span>

<span data-ttu-id="ac056-192">Der geschachtelte Ausdruck hat die folgende Form:</span><span class="sxs-lookup"><span data-stu-id="ac056-192">The nested expression is of the following form:</span></span>

```fsharp
builder.Run(builder.Delay(fun () -> {| cexpr |}))
```

<span data-ttu-id="ac056-193">Im obigen Code werden `Run` `Delay` die Aufrufe von und ausgelassen, wenn sie nicht in der Berechnungsausdruckbuilderklasse definiert sind.</span><span class="sxs-lookup"><span data-stu-id="ac056-193">In the above code, the calls to `Run` and `Delay` are omitted if they are not defined in the computation expression builder class.</span></span> <span data-ttu-id="ac056-194">Der Text des Berechnungsausdrucks, `{| cexpr |}`hier als bezeichnet , wird durch die in der folgenden Tabelle beschriebenen Übersetzungen in Aufrufe übersetzt, die die Methoden der Builder-Klasse betreffen.</span><span class="sxs-lookup"><span data-stu-id="ac056-194">The body of the computation expression, here denoted as `{| cexpr |}`, is translated into calls involving the methods of the builder class by the translations described in the following table.</span></span> <span data-ttu-id="ac056-195">Der Berechnungsausdruck `{| cexpr |}` wird rekursiv entsprechend diesen `expr` Übersetzungen definiert, wobei `cexpr` es sich um einen F-Ausdruck handelt und es sich um einen Berechnungsausdruck handelt.</span><span class="sxs-lookup"><span data-stu-id="ac056-195">The computation expression `{| cexpr |}` is defined recursively according to these translations where `expr` is an F# expression and `cexpr` is a computation expression.</span></span>

|<span data-ttu-id="ac056-196">Ausdruck</span><span class="sxs-lookup"><span data-stu-id="ac056-196">Expression</span></span>|<span data-ttu-id="ac056-197">Sprachübersetzung</span><span class="sxs-lookup"><span data-stu-id="ac056-197">Translation</span></span>|
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

<span data-ttu-id="ac056-198">Beschreibt in der `other-expr` vorherigen Tabelle einen Ausdruck, der nicht anderweitig in der Tabelle aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="ac056-198">In the previous table, `other-expr` describes an expression that is not otherwise listed in the table.</span></span> <span data-ttu-id="ac056-199">Eine Builderklasse muss nicht alle Methoden implementieren und alle in der vorherigen Tabelle aufgeführten Übersetzungen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="ac056-199">A builder class does not need to implement all of the methods and support all of the translations listed in the previous table.</span></span> <span data-ttu-id="ac056-200">Die nicht implementierten Konstrukte sind in Berechnungsausdrücken dieses Typs nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ac056-200">Those constructs that are not implemented are not available in computation expressions of that type.</span></span> <span data-ttu-id="ac056-201">Wenn Sie z. B. das `use` Schlüsselwort in Ihren Berechnungsausdrücken `Use` nicht unterstützen möchten, können Sie die Definition in Ihrer Builderklasse weglassen.</span><span class="sxs-lookup"><span data-stu-id="ac056-201">For example, if you do not want to support the `use` keyword in your computation expressions, you can omit the definition of `Use` in your builder class.</span></span>

<span data-ttu-id="ac056-202">Das folgende Codebeispiel zeigt einen Berechnungsausdruck, der eine Berechnung als eine Reihe von Schritten kapselt, die Schritt für Schritt ausgewertet werden können.</span><span class="sxs-lookup"><span data-stu-id="ac056-202">The following code example shows a computation expression that encapsulates a computation as a series of steps that can be evaluated one step at a time.</span></span> <span data-ttu-id="ac056-203">Ein diskriminierter Union-Typ , `OkOrException`, kodiert den Fehlerstatus des Ausdrucks, wie bisher ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="ac056-203">A discriminated union type, `OkOrException`, encodes the error state of the expression as evaluated so far.</span></span> <span data-ttu-id="ac056-204">Dieser Code veranschaulicht mehrere typische Muster, die Sie in Ihren Berechnungsausdrücken verwenden können, z. B. Boilerplate-Implementierungen einiger Builder-Methoden.</span><span class="sxs-lookup"><span data-stu-id="ac056-204">This code demonstrates several typical patterns that you can use in your computation expressions, such as boilerplate implementations of some of the builder methods.</span></span>

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

<span data-ttu-id="ac056-205">Ein Berechnungsausdruck hat einen zugrunde liegenden Typ, den der Ausdruck zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="ac056-205">A computation expression has an underlying type, which the expression returns.</span></span> <span data-ttu-id="ac056-206">Der zugrunde liegende Typ kann ein berechnetes Ergebnis oder eine verzögerte Berechnung darstellen, die durchgeführt werden kann, oder er kann eine Möglichkeit bieten, durch irgendeine Art von Auflistung zu iterieren.</span><span class="sxs-lookup"><span data-stu-id="ac056-206">The underlying type may represent a computed result or a delayed computation that can be performed, or it may provide a way to iterate through some type of collection.</span></span> <span data-ttu-id="ac056-207">Im vorherigen Beispiel war der zugrunde liegende Typ **Eventually**.</span><span class="sxs-lookup"><span data-stu-id="ac056-207">In the previous example, the underlying type was **Eventually**.</span></span> <span data-ttu-id="ac056-208">Bei einem Sequenzausdruck lautet <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>der zugrunde liegende Typ .</span><span class="sxs-lookup"><span data-stu-id="ac056-208">For a sequence expression, the underlying type is <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ac056-209">Bei einem Abfrageausdruck lautet <xref:System.Linq.IQueryable?displayProperty=nameWithType>der zugrunde liegende Typ .</span><span class="sxs-lookup"><span data-stu-id="ac056-209">For a query expression, the underlying type is <xref:System.Linq.IQueryable?displayProperty=nameWithType>.</span></span> <span data-ttu-id="ac056-210">Bei einem asynchronen Workflow lautet [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7)der zugrunde liegende Typ .</span><span class="sxs-lookup"><span data-stu-id="ac056-210">For an asynchronous workflow, the underlying type is [`Async`](https://msdn.microsoft.com/library/03eb4d12-a01a-4565-a077-5e83f17cf6f7).</span></span> <span data-ttu-id="ac056-211">Das `Async` Objekt stellt die Arbeit dar, die zum Berechnen des Ergebnisses ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac056-211">The `Async` object represents the work to be performed to compute the result.</span></span> <span data-ttu-id="ac056-212">Sie rufen z. B. auf, [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) um eine Berechnung auszuführen und das Ergebnis zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="ac056-212">For example, you call [`Async.RunSynchronously`](https://msdn.microsoft.com/library/0a6663a9-50f2-4d38-8bf3-cefd1a51fd6b) to execute a computation and return the result.</span></span>

## <a name="custom-operations"></a><span data-ttu-id="ac056-213">Benutzerdefinierte Vorgänge</span><span class="sxs-lookup"><span data-stu-id="ac056-213">Custom Operations</span></span>

<span data-ttu-id="ac056-214">Sie können einen benutzerdefinierten Vorgang für einen Berechnungsausdruck definieren und einen benutzerdefinierten Vorgang als Operator in einem Berechnungsausdruck verwenden.</span><span class="sxs-lookup"><span data-stu-id="ac056-214">You can define a custom operation on a computation expression and use a custom operation as an operator in a computation expression.</span></span> <span data-ttu-id="ac056-215">Sie können z. B. einen Abfrageoperator in einen Abfrageausdruck einschließen.</span><span class="sxs-lookup"><span data-stu-id="ac056-215">For example, you can include a query operator in a query expression.</span></span> <span data-ttu-id="ac056-216">Wenn Sie einen benutzerdefinierten Vorgang definieren, müssen Sie die Methoden Yield und For im Berechnungsausdruck definieren.</span><span class="sxs-lookup"><span data-stu-id="ac056-216">When you define a custom operation, you must define the Yield and For methods in the computation expression.</span></span> <span data-ttu-id="ac056-217">Um einen benutzerdefinierten Vorgang zu definieren, legen Sie ihn in [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19)eine Builderklasse für den Berechnungsausdruck, und wenden Sie dann die an.</span><span class="sxs-lookup"><span data-stu-id="ac056-217">To define a custom operation, put it in a builder class for the computation expression, and then apply the [`CustomOperationAttribute`](https://msdn.microsoft.com/library/199f3927-79df-484b-ba66-85f58cc49b19).</span></span> <span data-ttu-id="ac056-218">Dieses Attribut verwendet eine Zeichenfolge als Argument, d. h. den Namen, der in einem benutzerdefinierten Vorgang verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ac056-218">This attribute takes a string as an argument, which is the name to be used in a custom operation.</span></span> <span data-ttu-id="ac056-219">Dieser Name wird zu Beginn der öffnenden geschweiften Klammer des Berechnungsausdrucks in den Gültigkeitsbereich aufgenommen.</span><span class="sxs-lookup"><span data-stu-id="ac056-219">This name comes into scope at the start of the opening curly brace of the computation expression.</span></span> <span data-ttu-id="ac056-220">Daher sollten Sie keine Bezeichner verwenden, die denselben Namen wie ein benutzerdefinierter Vorgang in diesem Block haben.</span><span class="sxs-lookup"><span data-stu-id="ac056-220">Therefore, you shouldn’t use identifiers that have the same name as a custom operation in this block.</span></span> <span data-ttu-id="ac056-221">Vermeiden Sie beispielsweise die Verwendung von `all` `last` Bezeichnern wie z. B. oder in Abfrageausdrücken.</span><span class="sxs-lookup"><span data-stu-id="ac056-221">For example, avoid the use of identifiers such as `all` or `last` in query expressions.</span></span>

### <a name="extending-existing-builders-with-new-custom-operations"></a><span data-ttu-id="ac056-222">Erweitern vorhandener Builder mit neuen Custom Operations</span><span class="sxs-lookup"><span data-stu-id="ac056-222">Extending existing Builders with new Custom Operations</span></span>

<span data-ttu-id="ac056-223">Wenn Sie bereits über eine Builderklasse verfügen, können die benutzerdefinierten Vorgänge von außerhalb dieser Builderklasse erweitert werden.</span><span class="sxs-lookup"><span data-stu-id="ac056-223">If you already have a builder class, its custom operations can be extended from outside of this builder class.</span></span> <span data-ttu-id="ac056-224">Erweiterungen müssen in Modulen deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="ac056-224">Extensions must be declared in modules.</span></span> <span data-ttu-id="ac056-225">Namespaces können keine Erweiterungsmember enthalten, außer in derselben Datei und derselben Namespacedeklarationsgruppe, in der der Typ definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ac056-225">Namespaces cannot contain extension members except in the same file and the same namespace declaration group where the type is defined.</span></span>

<span data-ttu-id="ac056-226">Das folgende Beispiel zeigt die `Microsoft.FSharp.Linq.QueryBuilder` Erweiterung der vorhandenen Klasse.</span><span class="sxs-lookup"><span data-stu-id="ac056-226">The following example shows the extension of the existing `Microsoft.FSharp.Linq.QueryBuilder` class.</span></span>

```fsharp
type Microsoft.FSharp.Linq.QueryBuilder with

    [<CustomOperation("existsNot")>]
    member _.ExistsNot (source: QuerySource<'T, 'Q>, predicate) =
        Enumerable.Any (source.Source, Func<_,_>(predicate)) |> not
```

## <a name="see-also"></a><span data-ttu-id="ac056-227">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ac056-227">See also</span></span>

- [<span data-ttu-id="ac056-228">Sprachreferenz</span><span class="sxs-lookup"><span data-stu-id="ac056-228">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ac056-229">Asynchrone Workflows</span><span class="sxs-lookup"><span data-stu-id="ac056-229">Asynchronous Workflows</span></span>](asynchronous-workflows.md)
- [<span data-ttu-id="ac056-230">Sequenzen</span><span class="sxs-lookup"><span data-stu-id="ac056-230">Sequences</span></span>](https://msdn.microsoft.com/library/6b773b6b-9c9a-4af8-bd9e-d96585c166db)
- [<span data-ttu-id="ac056-231">Abfrageausdrücke</span><span class="sxs-lookup"><span data-stu-id="ac056-231">Query Expressions</span></span>](query-expressions.md)
