---
title: Inlinefunktionen (F#)
description: Informationen Sie zum F#-Inline-Funktionen verwenden, die direkt in den aufrufenden Code integriert werden.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: cb0addd1456af1ab97e249b9c5ece4d9f0818fa3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="inline-functions"></a><span data-ttu-id="8449f-103">Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="8449f-103">Inline Functions</span></span>

<span data-ttu-id="8449f-104">*Inlinefunktionen* sind Funktionen, die direkt in den aufrufenden Code integriert werden.</span><span class="sxs-lookup"><span data-stu-id="8449f-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>


## <a name="using-inline-functions"></a><span data-ttu-id="8449f-105">Verwendung von Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="8449f-105">Using Inline Functions</span></span>
<span data-ttu-id="8449f-106">Wenn Sie statische Typparameter verwenden, müssen alle Funktionen, die durch Typparameter parametrisiert werden Inline sein.</span><span class="sxs-lookup"><span data-stu-id="8449f-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="8449f-107">Damit wird sichergestellt, dass der Compiler diese Typparameter auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="8449f-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="8449f-108">Bei Verwendung von normalen generischen Typparametern besteht keine derartige Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="8449f-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="8449f-109">Als die Verwendung von Membereinschränkungen aktivieren, können Inline-Funktionen bei der Optimierung von Code hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="8449f-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="8449f-110">Übermäßige Verwendung von Inlinefunktionen kann jedoch den Code weniger beständiger gegen compileroptimierungen und die Implementierung von Bibliotheksfunktionen vorgenommenen Änderungen werden verursachen.</span><span class="sxs-lookup"><span data-stu-id="8449f-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="8449f-111">Aus diesem Grund sollten Sie vermeiden, Inline-Funktionen für die Optimierung verwenden, es sei denn, Sie, alle anderen Optimierungstechniken versucht haben.</span><span class="sxs-lookup"><span data-stu-id="8449f-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="8449f-112">Erstellen eine Inline-Funktion oder Methode kann die Leistung in einigen Fällen verbessern, aber das ist nicht immer die Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="8449f-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="8449f-113">Aus diesem Grund sollten Sie Leistungsindikatoren verwenden, um sicherzustellen, dass eine bestimmte Funktion Inline ausführenden tatsächlich eine positive Auswirkung haben.</span><span class="sxs-lookup"><span data-stu-id="8449f-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="8449f-114">Die `inline` Modifizierer auf Funktionen auf der obersten Ebene, auf der Modulebene oder auf Methodenebene in einer Klasse angewendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="8449f-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="8449f-115">Im folgenden Codebeispiel veranschaulicht eine Inlinefunktion auf der obersten Ebene, eine Inline-Instanzmethode und eine Inline-statische Methode.</span><span class="sxs-lookup"><span data-stu-id="8449f-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="8449f-116">Inlinefunktionen und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="8449f-116">Inline Functions and Type Inference</span></span>
<span data-ttu-id="8449f-117">Das Vorhandensein von `inline` wirkt sich auf den Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="8449f-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="8449f-118">Grund hierfür ist Inlinefunktionen Statisch aufgelöste Typparameter aufweisen können während nicht-Inline-Funktionen nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="8449f-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="8449f-119">Das folgende Codebeispiel zeigt einen Fall, in dem `inline` ist hilfreich, da Sie eine Funktion verwenden, die einen statisch aufgelösten Typparameter hat den `float` Konvertierungsoperator.</span><span class="sxs-lookup"><span data-stu-id="8449f-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="8449f-120">Ohne die `inline` Modifizierer, zwingt die Funktion ein bestimmtes Typs in diesem Fall wird der Typrückschluss `int`.</span><span class="sxs-lookup"><span data-stu-id="8449f-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="8449f-121">Mit der `inline` Modifizierer, die Funktion wird auch abgeleitet, dass Sie einen statisch aufgelösten Typparameter hat.</span><span class="sxs-lookup"><span data-stu-id="8449f-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="8449f-122">Mit der `inline` Modifizierer, der Typ wird abgeleitet, folgendermaßen:</span><span class="sxs-lookup"><span data-stu-id="8449f-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="8449f-123">Dies bedeutet, dass die Funktion einen beliebigen Typ akzeptiert, die eine Konvertierung in unterstützt **"float"**.</span><span class="sxs-lookup"><span data-stu-id="8449f-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>


## <a name="see-also"></a><span data-ttu-id="8449f-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8449f-124">See Also</span></span>
[<span data-ttu-id="8449f-125">Funktionen</span><span class="sxs-lookup"><span data-stu-id="8449f-125">Functions</span></span>](index.md)

[<span data-ttu-id="8449f-126">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="8449f-126">Constraints</span></span>](../generics/constraints.md)

[<span data-ttu-id="8449f-127">Statisch aufgelöste Typparameter</span><span class="sxs-lookup"><span data-stu-id="8449f-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
