---
title: Inlinefunktionen (F#)
description: Informationen Sie zum F#-Inline-Funktionen verwenden, die direkt in den aufrufenden Code integriert werden.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3fa31178-08f8-463d-9d41-d29220a90027
ms.openlocfilehash: 0489d411e2754eaab6a10ff0feb4405491b3b511
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2017
---
# <a name="inline-functions"></a><span data-ttu-id="abd96-104">Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="abd96-104">Inline Functions</span></span>

<span data-ttu-id="abd96-105">*Inlinefunktionen* sind Funktionen, die direkt in den aufrufenden Code integriert werden.</span><span class="sxs-lookup"><span data-stu-id="abd96-105">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="abd96-106">Verwendung von Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="abd96-106">Using Inline Functions</span></span>
<span data-ttu-id="abd96-107">Wenn Sie statische Typparameter verwenden, müssen alle Funktionen, die durch Typparameter parametrisiert werden Inline sein.</span><span class="sxs-lookup"><span data-stu-id="abd96-107">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="abd96-108">Damit wird sichergestellt, dass der Compiler diese Typparameter auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="abd96-108">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="abd96-109">Bei Verwendung von normalen generischen Typparametern besteht keine derartige Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="abd96-109">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="abd96-110">Als die Verwendung von Membereinschränkungen aktivieren, können Inline-Funktionen bei der Optimierung von Code hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="abd96-110">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="abd96-111">Übermäßige Verwendung von Inlinefunktionen kann jedoch den Code weniger beständiger gegen compileroptimierungen und die Implementierung von Bibliotheksfunktionen vorgenommenen Änderungen werden verursachen.</span><span class="sxs-lookup"><span data-stu-id="abd96-111">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="abd96-112">Aus diesem Grund sollten Sie vermeiden, Inline-Funktionen für die Optimierung verwenden, es sei denn, Sie, alle anderen Optimierungstechniken versucht haben.</span><span class="sxs-lookup"><span data-stu-id="abd96-112">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="abd96-113">Erstellen eine Inline-Funktion oder Methode kann die Leistung in einigen Fällen verbessern, aber das ist nicht immer die Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="abd96-113">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="abd96-114">Aus diesem Grund sollten Sie Leistungsindikatoren verwenden, um sicherzustellen, dass eine bestimmte Funktion Inline ausführenden tatsächlich eine positive Auswirkung haben.</span><span class="sxs-lookup"><span data-stu-id="abd96-114">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="abd96-115">Die `inline` Modifizierer auf Funktionen auf der obersten Ebene, auf der Modulebene oder auf Methodenebene in einer Klasse angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="abd96-115">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="abd96-116">Im folgenden Codebeispiel veranschaulicht eine Inlinefunktion auf der obersten Ebene, eine Inline-Instanzmethode und eine Inline-statische Methode.</span><span class="sxs-lookup"><span data-stu-id="abd96-116">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="abd96-117">Inlinefunktionen und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="abd96-117">Inline Functions and Type Inference</span></span>
<span data-ttu-id="abd96-118">Das Vorhandensein von `inline` wirkt sich auf den Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="abd96-118">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="abd96-119">Grund hierfür ist Inlinefunktionen Statisch aufgelöste Typparameter aufweisen können während nicht-Inline-Funktionen nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="abd96-119">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="abd96-120">Das folgende Codebeispiel zeigt einen Fall, in dem `inline` ist hilfreich, da Sie eine Funktion verwenden, die einen statisch aufgelösten Typparameter hat den `float` Konvertierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="abd96-120">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="abd96-121">Ohne die `inline` Modifizierer, zwingt die Funktion ein bestimmtes Typs in diesem Fall wird der Typrückschluss `int`.</span><span class="sxs-lookup"><span data-stu-id="abd96-121">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="abd96-122">Mit der `inline` Modifizierer, die Funktion wird auch abgeleitet, dass Sie einen statisch aufgelösten Typparameter hat.</span><span class="sxs-lookup"><span data-stu-id="abd96-122">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="abd96-123">Mit der `inline` Modifizierer, der Typ wird abgeleitet, folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="abd96-123">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="abd96-124">Dies bedeutet, dass die Funktion einen beliebigen Typ akzeptiert, die eine Konvertierung in unterstützt **"float"**.</span><span class="sxs-lookup"><span data-stu-id="abd96-124">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="abd96-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="abd96-125">See Also</span></span>
[<span data-ttu-id="abd96-126">Funktionen</span><span class="sxs-lookup"><span data-stu-id="abd96-126">Functions</span></span>](index.md)

[<span data-ttu-id="abd96-127">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="abd96-127">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="abd96-128">Statisch aufgelöste Typparameter</span><span class="sxs-lookup"><span data-stu-id="abd96-128">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
