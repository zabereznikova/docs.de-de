---
title: 'Rekursive Funktionen: Das rec-Schlüsselwort'
description: "Erfahren Sie, wie das F #-Schlüsselwort ' REC ' mit dem ' Let '-Schlüsselwort verwendet wird, um eine rekursive Funktion zu definieren."
ms.date: 08/12/2020
ms.openlocfilehash: 389357bd13cef39b1d07972c1a3167320b61612b
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558711"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="2bb5b-103">Rekursive Funktionen: Das rec-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="2bb5b-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="2bb5b-104">Das `rec` Schlüsselwort wird in Verbindung mit dem- `let` Schlüsselwort verwendet, um eine rekursive Funktion zu definieren.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="2bb5b-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="2bb5b-105">Syntax</span></span>

```fsharp
// Recursive function:
let rec function-nameparameter-list =
    function-body

// Mutually recursive functions:
let rec function1-nameparameter-list =
    function1-body

and function2-nameparameter-list =
    function2-body
...
```

## <a name="remarks"></a><span data-ttu-id="2bb5b-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="2bb5b-106">Remarks</span></span>

<span data-ttu-id="2bb5b-107">Rekursive Funktionen: Funktionen, die sich selbst anrufen, werden explizit in der Sprache F # mit dem- `rec` Schlüsselwort identifiziert.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-107">Recursive functions - functions that call themselves - are identified explicitly in the F# language with the `rec` keyword.</span></span> <span data-ttu-id="2bb5b-108">Mit dem- `rec` Schlüsselwort wird der Name der `let` Bindung im Textkörper verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-108">The `rec` keyword makes the name of the `let` binding available in its body.</span></span>

<span data-ttu-id="2bb5b-109">Das folgende Beispiel zeigt eine rekursive Funktion, die die *n*<sup>th</sup> -te-Datei "mebonacci" mit der mathematischen Definition berechnet.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-109">The following example shows a recursive function that computes the *n*<sup>th</sup> Fibonacci number using the mathematical definition.</span></span>

```fsharp
let fib n =
    match n with
    | 0 | 1 -> 1
    | n -> fib (n-1) + fib (n-2)
```

> [!NOTE]
> <span data-ttu-id="2bb5b-110">In der Praxis ist Code wie das vorherige Beispiel nicht ideal, da er bereits berechnete Werte nicht mehr berechnet.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-110">In practice, code like the previous sample is not ideal because it unecessarily recomputes values that have already been computed.</span></span> <span data-ttu-id="2bb5b-111">Dies liegt daran, dass es sich nicht um einen endrekursiven handelt, was in diesem Artikel ausführlicher erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-111">This is because it is not tail recursive, which is explained further in this article.</span></span>

<span data-ttu-id="2bb5b-112">Methoden sind implizit rekursiv innerhalb des Typs, in dem Sie definiert sind, d. h. es ist nicht erforderlich, das- `rec` Schlüsselwort hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-112">Methods are implicitly recursive within the type they are defined in, meaning there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="2bb5b-113">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2bb5b-113">For example:</span></span>

```fsharp
type MyClass() =
    member this.Fib(n) =
        match n with
        | 0 | 1 -> 1
        | n -> this.Fib(n-1) + this.Fib(n-2)
```

<span data-ttu-id="2bb5b-114">Let-Bindungen in Klassen sind jedoch nicht implizit rekursiv.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-114">Let bindings within classes are not implicitly recursive, though.</span></span> <span data-ttu-id="2bb5b-115">Für alle `let` gebundenen Funktionen ist das- `rec` Schlüsselwort erforderlich.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-115">All `let`-bound functions require the `rec` keyword.</span></span>

## <a name="tail-recursion"></a><span data-ttu-id="2bb5b-116">Endrekursion</span><span class="sxs-lookup"><span data-stu-id="2bb5b-116">Tail recursion</span></span>

<span data-ttu-id="2bb5b-117">Für einige rekursive Funktionen ist es erforderlich, eine "reine" Definition in eine "Pure"-Definition zu umgestalten, die [endrekursiv](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion)ist.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-117">For some recursive functions, it is necessary to refactor a more "pure" definition to one that is [tail recursive](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion).</span></span> <span data-ttu-id="2bb5b-118">Dies verhindert unnötige Neuberechnungen.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-118">This prevents unnecessary recomputations.</span></span> <span data-ttu-id="2bb5b-119">Beispielsweise kann der vorherige "fbonacci Number"-Generator wie folgt umgeschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="2bb5b-119">For example, the previous fibonacci number generator can be rewritten like this:</span></span>

```fsharp
let fib n =
    let rec loop acc1 acc2 n =
        match n with
        | 0 -> acc1
        | 1 -> acc2
        | _ ->
            loop acc2 (acc1 + acc2) (n - 1)
    loop 0 1 n
```

<span data-ttu-id="2bb5b-120">Dies ist eine kompliziertere Implementierung.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-120">This is a more complicated implementation.</span></span> <span data-ttu-id="2bb5b-121">Das Erstellen einer "fbonacci"-Nummer ist ein gutes Beispiel für einen "naive" Algorithmus, der mathematisch rein, aber in der Praxis ineffizient ist.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-121">Generating a fibonacci number is a great example of a "naive" algorithm that's mathematically pure but inefficient in practice.</span></span> <span data-ttu-id="2bb5b-122">Einige Aspekte machen es in F # effizient und bleiben weiterhin rekursiv definiert:</span><span class="sxs-lookup"><span data-stu-id="2bb5b-122">Several aspects make it efficient in F# while still remaining recursively defined:</span></span>

* <span data-ttu-id="2bb5b-123">Eine rekursive innere Funktion namens `loop` , bei der es sich um ein idiomatische F #-Muster handelt.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-123">A recursive inner function named `loop`, which is an idiomatic F# pattern.</span></span>
* <span data-ttu-id="2bb5b-124">Zwei akkumulatorparameter, die Akkumulations Werte an rekursive Aufrufe übergeben.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-124">Two accumulator parameters, which pass accumulate values to recursive calls.</span></span>
* <span data-ttu-id="2bb5b-125">Eine Prüfung auf den Wert von `n` , um eine bestimmte Kumulierung zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-125">A check on the value of `n` to return a specific accumulate.</span></span>

<span data-ttu-id="2bb5b-126">Wenn dieses Beispiel iterativ mit einer Schleife geschrieben wurde, sieht der Code mit zwei unterschiedlichen Werten ähnlich aus, bis eine bestimmte Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-126">If this example were written iteratively with a loop, the code would look similar with two different values accumulating numbers until a particular condition was met.</span></span>

<span data-ttu-id="2bb5b-127">Der Grund dafür ist, dass dies endrekursiv ist, da der rekursive Aufruf keine Werte in der Aufruf Stapel speichern muss.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-127">The reason why this is tail-recursive is because the recursive call does not need to save any values on the call stack.</span></span> <span data-ttu-id="2bb5b-128">Alle Zwischenwerte, die berechnet werden, werden über Eingaben in die innere Funktion akkumuliert.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-128">All intermediate values being calculated are accumulated via inputs to the inner function.</span></span> <span data-ttu-id="2bb5b-129">Dies ermöglicht es dem F #-Compiler auch, den Code so schnell wie möglich zu optimieren, wenn Sie etwas ähnliches wie eine-Schleife geschrieben hätten `while` .</span><span class="sxs-lookup"><span data-stu-id="2bb5b-129">This also allows the F# compiler to optimize the code to be just as fast as if you had written something like a `while` loop.</span></span>

<span data-ttu-id="2bb5b-130">Es ist üblich, F #-Code zu schreiben, der rekursiv etwas mit einer inneren und äußeren Funktion verarbeitet, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-130">It's common to write F# code that recursively processes something with an inner and outer function, as the previous example shows.</span></span> <span data-ttu-id="2bb5b-131">Die innere Funktion verwendet die Endrekursion, während die äußere Funktion über eine bessere Schnittstelle für Aufrufer verfügt.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-131">The inner function uses tail recursion, while the outer function has a better interface for callers.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="2bb5b-132">Gegenseitig rekursive Funktionen</span><span class="sxs-lookup"><span data-stu-id="2bb5b-132">Mutually Recursive Functions</span></span>

<span data-ttu-id="2bb5b-133">Manchmal sind Funktionen *gegenseitig rekursiv*. Dies bedeutet, dass Aufrufe einen Kreis bilden, wobei eine Funktion eine andere aufruft, die wiederum den ersten aufruft, wobei eine beliebige Anzahl von Aufrufen dazwischen ist.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-133">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="2bb5b-134">Sie müssen diese Funktionen in der eine Bindung zusammen definieren `let` , indem Sie das- `and` Schlüsselwort verwenden, um Sie miteinander zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-134">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="2bb5b-135">Das folgende Beispiel zeigt zwei gegenseitig rekursive Funktionen.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-135">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="recursive-values"></a><span data-ttu-id="2bb5b-136">Rekursive Werte</span><span class="sxs-lookup"><span data-stu-id="2bb5b-136">Recursive values</span></span>

<span data-ttu-id="2bb5b-137">Sie können auch einen `let` gebundenen Wert definieren, um rekursiv zu sein.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-137">You can also define a `let`-bound value to be recursive.</span></span> <span data-ttu-id="2bb5b-138">Dies erfolgt manchmal für die Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="2bb5b-138">This is sometimes done for logging.</span></span> <span data-ttu-id="2bb5b-139">Mit F # 5 und der- `nameof` Funktion können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="2bb5b-139">With F# 5 and the `nameof` function, you can do this:</span></span>

```fsharp
let rec nameDoubles = nameof nameDoubles + nameof nameDoubles
```

## <a name="see-also"></a><span data-ttu-id="2bb5b-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2bb5b-140">See also</span></span>

- [<span data-ttu-id="2bb5b-141">Funktionen</span><span class="sxs-lookup"><span data-stu-id="2bb5b-141">Functions</span></span>](index.md)
