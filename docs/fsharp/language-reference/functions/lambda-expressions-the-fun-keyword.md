---
title: 'Lambdaausdrücke: Das fun-Schlüsselwort (F#)'
description: Erfahren Sie, wie das 'Fun'-Schlüsselwort [F#] zu verwenden, um einen Lambda-Ausdruck zu definieren, der einer anonymen Funktion wird.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: f2f15a1b482ce3971d0b3d5ffc4f6dcc9ccf1569
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="364a1-103">Lambdaausdrücke: Das fun-Schlüsselwort (F#)</span><span class="sxs-lookup"><span data-stu-id="364a1-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="364a1-104">Die `fun` Schlüsselwort wird verwendet, um einen Lambda-Ausdruck, d. h. einer anonymen Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="364a1-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>


## <a name="syntax"></a><span data-ttu-id="364a1-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="364a1-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="364a1-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="364a1-106">Remarks</span></span>
<span data-ttu-id="364a1-107">Die *Parameterliste* besteht normalerweise aus Namen und optional die Typen der Parameter.</span><span class="sxs-lookup"><span data-stu-id="364a1-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="364a1-108">Allgemeiner gesagt ist der *Parameterliste* können bestehen keine f#-Muster.</span><span class="sxs-lookup"><span data-stu-id="364a1-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="364a1-109">Eine vollständige Liste der möglichen Muster finden Sie unter [Mustervergleich](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="364a1-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="364a1-110">Listen gültige Parameter werden in den folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="364a1-110">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="364a1-111">Die *Ausdruck* ist der Text der Funktion, von denen der letzte Ausdruck einen Rückgabewert generiert.</span><span class="sxs-lookup"><span data-stu-id="364a1-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="364a1-112">Die folgenden: Beispiele für gültige Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="364a1-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]
    
## <a name="using-lambda-expressions"></a><span data-ttu-id="364a1-113">Verwenden von Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="364a1-113">Using Lambda Expressions</span></span>
<span data-ttu-id="364a1-114">Lambda-Ausdrücke sind besonders nützlich, wenn Sie möchten, um Vorgänge auf eine Liste oder einer anderen Sammlung auszuführen und eine Funktion definieren den zusätzlichen Aufwand vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="364a1-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="364a1-115">Viele f#-Bibliotheksfunktionen nehmen Funktionswerte als Argumente ein, und es kann besonders praktisch, einen Lambda-Ausdruck in diesen Fällen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="364a1-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="364a1-116">Der folgende Code wendet einen Lambda-Ausdruck auf Elemente einer Liste.</span><span class="sxs-lookup"><span data-stu-id="364a1-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="364a1-117">In diesem Fall fügt 1 mit die anonyme Funktion auf jedes Element einer Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="364a1-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]
    
## <a name="see-also"></a><span data-ttu-id="364a1-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="364a1-118">See Also</span></span>
[<span data-ttu-id="364a1-119">Funktionen</span><span class="sxs-lookup"><span data-stu-id="364a1-119">Functions</span></span>](index.md)
