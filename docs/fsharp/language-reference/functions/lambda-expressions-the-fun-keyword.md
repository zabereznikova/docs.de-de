---
title: 'Lambda-Ausdrücke: Das Fun-Schlüsselwort'
description: Erfahren Sie, wie Sie mit der F# "Fun"-Schlüsselwort, um ein Lambda-Ausdruck definieren, die eine anonyme Funktion ist.
ms.date: 05/16/2016
ms.openlocfilehash: 6ad15173bb8643bff330e3ca3823cba5d43ad445
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53614460"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="fb407-103">Lambda-Ausdrücke: Das Fun-Schlüsselwort (F#)</span><span class="sxs-lookup"><span data-stu-id="fb407-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="fb407-104">Die `fun` -Schlüsselwort wird verwendet, um einen Lambdaausdruck, d. h. eine anonyme Funktion zu definieren.</span><span class="sxs-lookup"><span data-stu-id="fb407-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="fb407-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fb407-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="fb407-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fb407-106">Remarks</span></span>

<span data-ttu-id="fb407-107">Die *Parameterliste* mit Namen und optional die Typen der Parameter in der Regel besteht.</span><span class="sxs-lookup"><span data-stu-id="fb407-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="fb407-108">Allgemeiner ausgedrückt, die *Parameterliste* bestehen alle F# Muster.</span><span class="sxs-lookup"><span data-stu-id="fb407-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="fb407-109">Eine vollständige Liste der möglichen Muster finden Sie unter [Musterabgleich](../pattern-matching.md).</span><span class="sxs-lookup"><span data-stu-id="fb407-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="fb407-110">Liste der gültigen Parameter enthalten die folgenden Beispielen.</span><span class="sxs-lookup"><span data-stu-id="fb407-110">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="fb407-111">Die *Ausdruck* ist der Text der Funktion, von denen der letzte Ausdruck einen Wert zurückgegeben generiert.</span><span class="sxs-lookup"><span data-stu-id="fb407-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="fb407-112">Die folgenden: Beispiele für gültige Lambda-Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="fb407-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="fb407-113">Verwenden von Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="fb407-113">Using Lambda Expressions</span></span>

<span data-ttu-id="fb407-114">Lambda-Ausdrücke sind besonders nützlich, wenn Sie die Vorgänge auf eine Liste oder einer anderen Sammlung aus, und Definieren einer Funktion den zusätzlichen Aufwand vermeiden möchten, verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="fb407-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="fb407-115">Viele F# Library-Funktionen nehmen die Werte von Funktionen als Argumente ein, und es kann sein, insbesondere dann hilfreich, einen Lambda-Ausdruck in diesen Fällen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fb407-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="fb407-116">Der folgende Code gilt einen Lambda-Ausdruck, für die Elemente einer Liste.</span><span class="sxs-lookup"><span data-stu-id="fb407-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="fb407-117">In diesem Fall wird die anonyme Funktion 1 auf jedes Element einer Liste hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fb407-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="fb407-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb407-118">See also</span></span>

- [<span data-ttu-id="fb407-119">Funktionen</span><span class="sxs-lookup"><span data-stu-id="fb407-119">Functions</span></span>](index.md)