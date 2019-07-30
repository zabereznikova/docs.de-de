---
title: 'Lambda-Ausdrücke: Das fun-Schlüsselwort'
description: Erfahren Sie, wie Sie F# das Schlüsselwort "Fun" verwenden, um einen Lambda-Ausdruck zu definieren, der eine anonyme Funktion ist.
ms.date: 05/16/2016
ms.openlocfilehash: 9818724686dd83a7e352fb36819289fa19b002df
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630666"
---
# <a name="lambda-expressions-the-fun-keyword-f"></a><span data-ttu-id="f6718-103">Lambda-Ausdrücke: Das Fun-SchlüsselF#Wort ()</span><span class="sxs-lookup"><span data-stu-id="f6718-103">Lambda Expressions: The fun Keyword (F#)</span></span>

<span data-ttu-id="f6718-104">Das `fun` -Schlüsselwort wird verwendet, um einen Lambda-Ausdruck, d. h. eine anonyme Funktion, zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f6718-104">The `fun` keyword is used to define a lambda expression, that is, an anonymous function.</span></span>

## <a name="syntax"></a><span data-ttu-id="f6718-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f6718-105">Syntax</span></span>

```fsharp
fun parameter-list -> expression
```

## <a name="remarks"></a><span data-ttu-id="f6718-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6718-106">Remarks</span></span>

<span data-ttu-id="f6718-107">Die *Parameter-List* besteht in der Regel aus Namen und optional Typen von Parametern.</span><span class="sxs-lookup"><span data-stu-id="f6718-107">The *parameter-list* typically consists of names and, optionally, types of parameters.</span></span> <span data-ttu-id="f6718-108">Im Allgemeinen kann die *Parameter-List* aus beliebigen F# Mustern bestehen.</span><span class="sxs-lookup"><span data-stu-id="f6718-108">More generally, the *parameter-list* can be composed of any F# patterns.</span></span> <span data-ttu-id="f6718-109">Eine vollständige Liste möglicher Muster finden Sie unter [Muster](../pattern-matching.md)Abgleich.</span><span class="sxs-lookup"><span data-stu-id="f6718-109">For a full list of possible patterns, see [Pattern Matching](../pattern-matching.md).</span></span> <span data-ttu-id="f6718-110">In den folgenden Beispielen finden Sie Listen gültiger Parameter.</span><span class="sxs-lookup"><span data-stu-id="f6718-110">Lists of valid parameters include the following examples.</span></span>

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

<span data-ttu-id="f6718-111">Der *Ausdruck* ist der Hauptteil der Funktion. der letzte Ausdruck von, der einen Rückgabewert generiert.</span><span class="sxs-lookup"><span data-stu-id="f6718-111">The *expression* is the body of the function, the last expression of which generates a return value.</span></span> <span data-ttu-id="f6718-112">Beispiele für gültige Lambda-Ausdrücke:</span><span class="sxs-lookup"><span data-stu-id="f6718-112">Examples of valid lambda expressions include the following:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet301.fs)]

## <a name="using-lambda-expressions"></a><span data-ttu-id="f6718-113">Verwenden von Lambdaausdrücken</span><span class="sxs-lookup"><span data-stu-id="f6718-113">Using Lambda Expressions</span></span>

<span data-ttu-id="f6718-114">Lambda-Ausdrücke sind besonders nützlich, wenn Sie Vorgänge für eine Liste oder eine andere Auflistung ausführen möchten und die zusätzliche Arbeit beim Definieren einer Funktion vermeiden möchten.</span><span class="sxs-lookup"><span data-stu-id="f6718-114">Lambda expressions are especially useful when you want to perform operations on a list or other collection and want to avoid the extra work of defining a function.</span></span> <span data-ttu-id="f6718-115">Viele F# Library-Funktionen nehmen die Werte von Funktionen als Argumente ein, und es kann sein, insbesondere dann hilfreich, einen Lambda-Ausdruck in diesen Fällen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6718-115">Many F# library functions take function values as arguments, and it can be especially convenient to use a lambda expression in those cases.</span></span> <span data-ttu-id="f6718-116">Der folgende Code wendet einen Lambda-Ausdruck auf Elemente einer Liste an.</span><span class="sxs-lookup"><span data-stu-id="f6718-116">The following code applies a lambda expression to elements of a list.</span></span> <span data-ttu-id="f6718-117">In diesem Fall fügt die anonyme Funktion jedem Element einer Liste 1 hinzu.</span><span class="sxs-lookup"><span data-stu-id="f6718-117">In this case, the anonymous function adds 1 to every element of a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet302.fs)]

## <a name="see-also"></a><span data-ttu-id="f6718-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6718-118">See also</span></span>

- [<span data-ttu-id="f6718-119">Funktionen</span><span class="sxs-lookup"><span data-stu-id="f6718-119">Functions</span></span>](index.md)
