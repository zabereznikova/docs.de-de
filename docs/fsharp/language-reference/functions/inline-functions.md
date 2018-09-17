---
title: Inlinefunktionen (F#)
description: Erfahren Sie, wie Sie mit F#-Inline-Funktionen, die direkt in den aufrufenden Code integriert sind.
ms.date: 05/16/2016
ms.openlocfilehash: 47fca0fe34630792aeb0908b0cee02a927e2567d
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2018
ms.locfileid: "45745944"
---
# <a name="inline-functions"></a><span data-ttu-id="ae7a0-103">Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="ae7a0-103">Inline Functions</span></span>

<span data-ttu-id="ae7a0-104">*Inlinefunktionen* sind Funktionen, die direkt in den aufrufenden Code integriert werden.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="ae7a0-105">Verwendung von Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="ae7a0-105">Using Inline Functions</span></span>

<span data-ttu-id="ae7a0-106">Wenn Sie statische Typparameter verwenden, müssen jede Funktion, die durch den Typparameter parametrisiert werden Inline sein.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="ae7a0-107">Dadurch wird sichergestellt, dass der Compiler diese Typparameter auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="ae7a0-108">Wenn Sie normale generischen Typparameter verwenden, besteht keine derartige Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="ae7a0-109">Als die Verwendung der Member-Einschränkungen aktivieren, können Inline-Funktionen in die Optimierung von Code hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="ae7a0-110">Übermäßiger Verwendung von Inlinefunktionen kann jedoch zu Ihrem Code weniger auf Änderungen compileroptimierungen und die Implementierung der Library-Funktionen zum Schutz vor Angriffen führen.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="ae7a0-111">Aus diesem Grund sollten Sie vermeiden, verwenden Inline-Funktionen für die Optimierung, es sei denn, Sie, alle anderen Techniken zur Optimierung versucht haben.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="ae7a0-112">Erstellen eine Funktion oder Methode Inline kann manchmal die Leistung verbessern, aber das ist nicht immer der Fall.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="ae7a0-113">Aus diesem Grund sollten Sie leistungsmessungen verwenden, um sicherzustellen, dass bestimmte Funktion Inline erstellen einen positiven Effekt in der Tat verfügt.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="ae7a0-114">Die `inline` Modifizierer auf Funktionen auf der obersten Ebene, auf der Modulebene oder auf der Ebene der in einer Klasse angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="ae7a0-115">Im folgenden Codebeispiel wird veranschaulicht, auf der obersten Ebene, die Methode eine Inline-Instanz und eine statische Inline-Methode eine Inline-Funktion.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="ae7a0-116">Inlinefunktionen und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="ae7a0-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="ae7a0-117">Das Vorhandensein von `inline` wirkt sich auf den Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="ae7a0-118">Dies ist da Inlinefunktionen Statisch aufgelöste Typparameter aufweisen können, während nicht-Inline-Funktionen nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="ae7a0-119">Das folgende Codebeispiel zeigt einen Fall, in denen `inline` ist hilfreich, da Sie eine Funktion verwenden, der einen statisch aufgelösten Typparameter hat den `float` Konvertierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="ae7a0-120">Ohne die `inline` Modifizierer, zwingt die Funktion ein bestimmtes Typs in diesem Fall wird der Typrückschluss `int`.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="ae7a0-121">Dabei sollen die `inline` Modifizierer, die Funktion so haben einen statisch aufgelösten Typparameter abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="ae7a0-122">Mit der `inline` Modifizierer, der Typ abgeleitet wird, werden die folgenden:</span><span class="sxs-lookup"><span data-stu-id="ae7a0-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="ae7a0-123">Dies bedeutet, dass die Funktion jeden Typ akzeptiert, die eine Konvertierung in unterstützt **"float"**.</span><span class="sxs-lookup"><span data-stu-id="ae7a0-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="ae7a0-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ae7a0-124">See also</span></span>

- [<span data-ttu-id="ae7a0-125">Funktionen</span><span class="sxs-lookup"><span data-stu-id="ae7a0-125">Functions</span></span>](index.md)
- [<span data-ttu-id="ae7a0-126">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="ae7a0-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="ae7a0-127">Statisch aufgelöste Typparameter</span><span class="sxs-lookup"><span data-stu-id="ae7a0-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
