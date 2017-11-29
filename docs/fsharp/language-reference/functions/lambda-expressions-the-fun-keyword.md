---
title: "Lambdaausdrücke: Das fun-Schlüsselwort (F#)"
description: "Erfahren Sie, wie das 'Fun'-Schlüsselwort [F#] zu verwenden, um einen Lambda-Ausdruck zu definieren, der einer anonymen Funktion wird."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: e5d3565c-d7cc-433f-a619-886ed92523a7
ms.openlocfilehash: 09f1c1787bbb4b86ec40f9e973e08104919631aa
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="6e408-104">Lambdaausdrücke: Das fun-Schlüsselwort (F#)</span><span class="sxs-lookup"><span data-stu-id="6e408-104">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="6e408-105">Die `fun` Schlüsselwort wird verwendet, um einen Lambda-Ausdruck, d. h. einer anonymen Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="6e408-105">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>


## <a name="syntax"></a><span data-ttu-id="6e408-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6e408-106">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="6e408-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6e408-107">Remarks</span></span>
<span data-ttu-id="6e408-108">Die *Parameterliste* besteht normalerweise aus Namen und optional die Typen der Parameter.</span><span class="sxs-lookup"><span data-stu-id="6e408-108">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="6e408-109">Allgemeiner gesagt ist der *Parameterliste* können bestehen keine f#-Muster.</span><span class="sxs-lookup"><span data-stu-id="6e408-109">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="6e408-110">Eine vollständige Liste der möglichen Muster finden Sie unter [Mustervergleich](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="6e408-110">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="6e408-111">Listen gültige Parameter werden in den folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="6e408-111">Lists of valid parameters include the following examples.</span></span>

```fsharp
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …
```

<span data-ttu-id="6e408-112">Die *Ausdruck* ist der Text der Funktion, von denen der letzte Ausdruck einen Rückgabewert generiert.</span><span class="sxs-lookup"><span data-stu-id="6e408-112">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="6e408-113">Die folgenden: Beispiele für gültige Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="6e408-113">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a><span data-ttu-id="6e408-114">Verwenden von Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="6e408-114">Using Lambda Expressions</span></span>
<span data-ttu-id="6e408-115">Lambda-Ausdrücke sind besonders nützlich, wenn Sie möchten, um Vorgänge auf eine Liste oder einer anderen Sammlung auszuführen und eine Funktion definieren den zusätzlichen Aufwand vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="6e408-115">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="6e408-116">Viele f#-Bibliotheksfunktionen nehmen Funktionswerte als Argumente ein, und es kann besonders praktisch, einen Lambda-Ausdruck in diesen Fällen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6e408-116">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="6e408-117">Der folgende Code wendet einen Lambda-Ausdruck auf Elemente einer Liste.</span><span class="sxs-lookup"><span data-stu-id="6e408-117">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="6e408-118">In diesem Fall fügt 1 mit die anonyme Funktion auf jedes Element einer Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="6e408-118">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="6e408-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6e408-119">See Also</span></span>
[<span data-ttu-id="6e408-120">Funktionen</span><span class="sxs-lookup"><span data-stu-id="6e408-120">Functions</span></span>](index.md)
