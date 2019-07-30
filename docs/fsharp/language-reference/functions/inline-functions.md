---
title: Inlinefunktionen
description: Erfahren Sie, wie F# Inline Funktionen verwendet werden, die direkt in den aufrufenden Code integriert sind.
ms.date: 05/16/2016
ms.openlocfilehash: 2830d1ada5b3005c3fcae975a44e85a7c84554f7
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630677"
---
# <a name="inline-functions"></a><span data-ttu-id="7a501-103">Inlinefunktionen</span><span class="sxs-lookup"><span data-stu-id="7a501-103">Inline Functions</span></span>

<span data-ttu-id="7a501-104">*Inline Funktionen* sind Funktionen, die direkt in den aufrufenden Code integriert sind.</span><span class="sxs-lookup"><span data-stu-id="7a501-104">*Inline functions* are functions that are integrated directly into the calling code.</span></span>

## <a name="using-inline-functions"></a><span data-ttu-id="7a501-105">Verwenden von Inline Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a501-105">Using Inline Functions</span></span>

<span data-ttu-id="7a501-106">Wenn Sie statische Typparameter verwenden, müssen alle Funktionen, die von Typparametern parametrisiert werden, Inline sein.</span><span class="sxs-lookup"><span data-stu-id="7a501-106">When you use static type parameters, any functions that are parameterized by type parameters must be inline.</span></span> <span data-ttu-id="7a501-107">Dadurch wird sichergestellt, dass der Compiler diese Typparameter auflösen kann.</span><span class="sxs-lookup"><span data-stu-id="7a501-107">This guarantees that the compiler can resolve these type parameters.</span></span> <span data-ttu-id="7a501-108">Wenn Sie gewöhnliche generische Typparameter verwenden, gibt es keine derartige Einschränkung.</span><span class="sxs-lookup"><span data-stu-id="7a501-108">When you use ordinary generic type parameters, there is no such restriction.</span></span>

<span data-ttu-id="7a501-109">Wenn Sie die Verwendung von Element Einschränkungen nicht aktivieren, können Inline Funktionen beim Optimieren von Code hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="7a501-109">Other than enabling the use of member constraints, inline functions can be helpful in optimizing code.</span></span> <span data-ttu-id="7a501-110">Die übermäßige Verwendung von Inline Funktionen kann jedoch dazu führen, dass Ihr Code weniger gegen Änderungen an Compileroptimierungen und die Implementierung von Bibliotheksfunktionen ist.</span><span class="sxs-lookup"><span data-stu-id="7a501-110">However, overuse of inline functions can cause your code to be less resistant to changes in compiler optimizations and the implementation of library functions.</span></span> <span data-ttu-id="7a501-111">Aus diesem Grund sollten Sie die Verwendung von Inline Funktionen für die Optimierung vermeiden, es sei denn, Sie haben alle anderen Optimierungstechniken ausprobiert.</span><span class="sxs-lookup"><span data-stu-id="7a501-111">For this reason, you should avoid using inline functions for optimization unless you have tried all other optimization techniques.</span></span> <span data-ttu-id="7a501-112">Wenn eine Funktion oder Methode Inline ist, kann die Leistung manchmal verbessert werden, dies ist jedoch nicht immer der Fall.</span><span class="sxs-lookup"><span data-stu-id="7a501-112">Making a function or method inline can sometimes improve performance, but that is not always the case.</span></span> <span data-ttu-id="7a501-113">Daher sollten Sie auch Leistungsmessungen verwenden, um zu überprüfen, ob das Erstellen einer bestimmten Funktion in der Tat eine positive Wirkung hat.</span><span class="sxs-lookup"><span data-stu-id="7a501-113">Therefore, you should also use performance measurements to verify that making any given function inline does in fact have a positive effect.</span></span>

<span data-ttu-id="7a501-114">Der `inline` -Modifizierer kann auf Funktionen auf der obersten Ebene, auf Modulebene oder auf Methoden Ebene in einer Klasse angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="7a501-114">The `inline` modifier can be applied to functions at the top level, at the module level, or at the method level in a class.</span></span>

<span data-ttu-id="7a501-115">Im folgenden Codebeispiel wird eine Inline Funktion auf oberster Ebene, eine Inline-Instanzmethode und eine statische Inline-Methode veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7a501-115">The following code example illustrates an inline function at the top level, an inline instance method, and an inline static method.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet201.fs)]

## <a name="inline-functions-and-type-inference"></a><span data-ttu-id="7a501-116">Inline Funktionen und Typrückschluss</span><span class="sxs-lookup"><span data-stu-id="7a501-116">Inline Functions and Type Inference</span></span>

<span data-ttu-id="7a501-117">Das vorhanden sein `inline` von beeinflusst den Typrückschluss.</span><span class="sxs-lookup"><span data-stu-id="7a501-117">The presence of `inline` affects type inference.</span></span> <span data-ttu-id="7a501-118">Dies liegt daran, dass Inline Funktionen statisch aufgelöste Typparameter aufweisen können, während nicht Inline Funktionen nicht.</span><span class="sxs-lookup"><span data-stu-id="7a501-118">This is because inline functions can have statically resolved type parameters, whereas non-inline functions cannot.</span></span> <span data-ttu-id="7a501-119">Das folgende Codebeispiel zeigt einen Fall, `inline` bei dem hilfreich ist, da Sie eine Funktion verwenden, die einen statisch aufgelösten Typparameter `float` aufweist, den Konvertierungs Operator.</span><span class="sxs-lookup"><span data-stu-id="7a501-119">The following code example shows a case where `inline` is helpful because you are using a function that has a statically resolved type parameter, the `float` conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

<span data-ttu-id="7a501-120">Ohne den `inline` -Modifizierer zwingt der Typrückschluss, dass die Funktion einen bestimmten Typ annimmt `int`, in diesem Fall.</span><span class="sxs-lookup"><span data-stu-id="7a501-120">Without the `inline` modifier, type inference forces the function to take a specific type, in this case `int`.</span></span> <span data-ttu-id="7a501-121">Mit dem `inline` -Modifizierer wird jedoch auch die-Funktion abgeleitet, um einen statisch aufgelösten Typparameter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="7a501-121">But with the `inline` modifier, the function is also inferred to have a statically resolved type parameter.</span></span> <span data-ttu-id="7a501-122">Mit dem `inline` -Modifizierer wird der Typ wie folgt abgeleitet:</span><span class="sxs-lookup"><span data-stu-id="7a501-122">With the `inline` modifier, the type is inferred to be the following:</span></span>

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

<span data-ttu-id="7a501-123">Dies bedeutet, dass die Funktion einen beliebigen Typ akzeptiert, der eine Konvertierung in **float**unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7a501-123">This means that the function accepts any type that supports a conversion to **float**.</span></span>

## <a name="see-also"></a><span data-ttu-id="7a501-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7a501-124">See also</span></span>

- [<span data-ttu-id="7a501-125">Funktionen</span><span class="sxs-lookup"><span data-stu-id="7a501-125">Functions</span></span>](index.md)
- [<span data-ttu-id="7a501-126">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="7a501-126">Constraints</span></span>](../generics/constraints.md)
- [<span data-ttu-id="7a501-127">Statisch aufgelöste Typparameter</span><span class="sxs-lookup"><span data-stu-id="7a501-127">Statically Resolved Type Parameters</span></span>](../generics/statically-resolved-type-parameters.md)
