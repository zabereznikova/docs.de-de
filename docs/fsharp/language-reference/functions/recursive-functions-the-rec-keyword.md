---
title: 'Rekursive Funktionen: Das rec-Schlüsselwort'
description: "Erfahren Sie, wie das F #-Schlüsselwort ' REC ' mit dem ' Let '-Schlüsselwort verwendet wird, um eine rekursive Funktion zu definieren."
ms.date: 05/16/2016
ms.openlocfilehash: c2374f90b4585327c6f5208a3d6bca75a23d0cbb
ms.sourcegitcommit: 7499bdb428d63ed0e19e97f54d3d576c41598659
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "87455658"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="5b712-103">Rekursive Funktionen: Das rec-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="5b712-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="5b712-104">Das `rec` Schlüsselwort wird in Verbindung mit dem- `let` Schlüsselwort verwendet, um eine rekursive Funktion zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5b712-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="5b712-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b712-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="5b712-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5b712-106">Remarks</span></span>

<span data-ttu-id="5b712-107">Rekursive Funktionen, die sich selbst aufzurufen, werden explizit in der F #-Sprache identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5b712-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="5b712-108">Dadurch ist der zu definierenden identierer im Gültigkeitsbereich der Funktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b712-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="5b712-109">Der folgende Code veranschaulicht eine rekursive Funktion, die die *n*<sup>th</sup> -te-Datei "mebonacci" mit der mathematischen Definition berechnet.</span><span class="sxs-lookup"><span data-stu-id="5b712-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number using the mathematical definition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="5b712-110">In der Praxis ist Code wie das vorherige Beispiel nicht ideal, da er bereits berechnete Werte nicht mehr berechnet.</span><span class="sxs-lookup"><span data-stu-id="5b712-110">In practice, code like the previous sample is not ideal because it unecessarily recomputes values that have already been computed.</span></span> <span data-ttu-id="5b712-111">Dies liegt daran, dass es sich nicht um einen endrekursiven handelt, was in diesem Artikel ausführlicher erläutert wird.</span><span class="sxs-lookup"><span data-stu-id="5b712-111">This is because it is not tail recursive, which is explained further in this article.</span></span>

<span data-ttu-id="5b712-112">Methoden sind implizit rekursiv innerhalb des Typs. Es ist nicht erforderlich, das- `rec` Schlüsselwort hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="5b712-112">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="5b712-113">Let-Bindungen in Klassen sind nicht implizit rekursiv.</span><span class="sxs-lookup"><span data-stu-id="5b712-113">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="tail-recursion"></a><span data-ttu-id="5b712-114">Endrekursion</span><span class="sxs-lookup"><span data-stu-id="5b712-114">Tail recursion</span></span>

<span data-ttu-id="5b712-115">Für einige rekursive Funktionen ist es erforderlich, eine "reine" Definition in eine "Pure"-Definition zu umgestalten, die [endrekursiv](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion)ist.</span><span class="sxs-lookup"><span data-stu-id="5b712-115">For some recursive functions, it is necessary to refactor a more "pure" definition to one that is [tail recursive](https://cs.stackexchange.com/questions/6230/what-is-tail-recursion).</span></span> <span data-ttu-id="5b712-116">Dies verhindert unnötige Neuberechnungen.</span><span class="sxs-lookup"><span data-stu-id="5b712-116">This prevents unnecessary recomputations.</span></span> <span data-ttu-id="5b712-117">Beispielsweise kann der vorherige "fbonacci Number"-Generator wie folgt umgeschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="5b712-117">For example, the previous fibonacci number generator can be rewritten like this:</span></span>

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

<span data-ttu-id="5b712-118">Dies ist eine kompliziertere Implementierung.</span><span class="sxs-lookup"><span data-stu-id="5b712-118">This is a more complicated implementation.</span></span> <span data-ttu-id="5b712-119">Das Erstellen einer "fbonacci"-Nummer ist ein gutes Beispiel für einen "naive" Algorithmus, der mathematisch rein, aber in der Praxis ineffizient ist.</span><span class="sxs-lookup"><span data-stu-id="5b712-119">Generating a fibonacci number is a great example of a "naive" algorithm that's mathematically pure but inefficient in practice.</span></span> <span data-ttu-id="5b712-120">Einige Aspekte machen es in F # effizient und bleiben weiterhin rekursiv definiert:</span><span class="sxs-lookup"><span data-stu-id="5b712-120">Several aspects make it efficient in F# while still remaining recursively defined:</span></span>

* <span data-ttu-id="5b712-121">Eine rekursive innere Funktion namens `loop` , bei der es sich um ein idiomatische F #-Muster handelt.</span><span class="sxs-lookup"><span data-stu-id="5b712-121">A recursive inner function named `loop`, which is an idiomatic F# pattern.</span></span>
* <span data-ttu-id="5b712-122">Zwei akkumulatorparameter, die Akkumulations Werte an rekursive Aufrufe übergeben.</span><span class="sxs-lookup"><span data-stu-id="5b712-122">Two accumulator parameters, which pass accumulate values to recursive calls.</span></span>
* <span data-ttu-id="5b712-123">Eine Prüfung auf den Wert von `n` , um eine bestimmte Kumulierung zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="5b712-123">A check on the value of `n` to return a specific accumulate.</span></span>

<span data-ttu-id="5b712-124">Wenn dieses Beispiel iterativ mit einer Schleife geschrieben wurde, sieht der Code mit zwei unterschiedlichen Werten ähnlich aus, bis eine bestimmte Bedingung erfüllt ist.</span><span class="sxs-lookup"><span data-stu-id="5b712-124">If this example were written iteratively with a loop, the code would look similar with two different values accumulating numbers until a particular condition was met.</span></span>

<span data-ttu-id="5b712-125">Der Grund dafür ist, dass dies endrekursiv ist, da der rekursive Aufruf keine Werte in der Aufruf Stapel speichern muss.</span><span class="sxs-lookup"><span data-stu-id="5b712-125">The reason why this is tail-recursive is because the recursive call does not need to save any values on the call stack.</span></span> <span data-ttu-id="5b712-126">Alle Zwischenwerte, die berechnet werden, werden über Eingaben in die innere Funktion akkumuliert.</span><span class="sxs-lookup"><span data-stu-id="5b712-126">All intermediate values being calculated are accumulated via inputs to the inner function.</span></span> <span data-ttu-id="5b712-127">Dies ermöglicht es dem F #-Compiler auch, den Code so schnell wie möglich zu optimieren, wenn Sie etwas ähnliches wie eine-Schleife geschrieben hätten `while` .</span><span class="sxs-lookup"><span data-stu-id="5b712-127">This also allows the F# compiler to optimize the code to be just as fast as if you had written something like a `while` loop.</span></span>

<span data-ttu-id="5b712-128">Es ist üblich, F #-Code zu schreiben, der rekursiv etwas mit einer inneren und äußeren Funktion verarbeitet, wie im vorherigen Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="5b712-128">It's common to write F# code that recursively processes something with an inner and outer function, as the previous example shows.</span></span> <span data-ttu-id="5b712-129">Die innere Funktion verwendet die Endrekursion, während die äußere Funktion über eine bessere Schnittstelle für Aufrufer verfügt.</span><span class="sxs-lookup"><span data-stu-id="5b712-129">The inner function uses tail recursion, while the outer function has a better interface for callers.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="5b712-130">Gegenseitig rekursive Funktionen</span><span class="sxs-lookup"><span data-stu-id="5b712-130">Mutually Recursive Functions</span></span>

<span data-ttu-id="5b712-131">Manchmal sind Funktionen *gegenseitig rekursiv*. Dies bedeutet, dass Aufrufe einen Kreis bilden, wobei eine Funktion eine andere aufruft, die wiederum den ersten aufruft, wobei eine beliebige Anzahl von Aufrufen dazwischen ist.</span><span class="sxs-lookup"><span data-stu-id="5b712-131">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="5b712-132">Sie müssen diese Funktionen in der eine Bindung zusammen definieren `let` , indem Sie das- `and` Schlüsselwort verwenden, um Sie miteinander zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="5b712-132">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="5b712-133">Das folgende Beispiel zeigt zwei gegenseitig rekursive Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5b712-133">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="5b712-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5b712-134">See also</span></span>

- [<span data-ttu-id="5b712-135">Funktionen</span><span class="sxs-lookup"><span data-stu-id="5b712-135">Functions</span></span>](index.md)
