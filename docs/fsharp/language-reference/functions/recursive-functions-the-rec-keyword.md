---
title: 'Rekursive Funktionen: Das Rec-Schlüsselwort'
description: Erfahren Sie, F# wie das Schlüsselwort "Rec" mit dem Schlüsselwort "Let" verwendet wird, um eine rekursive Funktion zu definieren.
ms.date: 05/16/2016
ms.openlocfilehash: 7edaa7206b2109c7b1a405624b9b2330968f9c52
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630650"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="64d2d-103">Rekursive Funktionen: Das Rec-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="64d2d-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="64d2d-104">Das `rec` Schlüsselwort wird in Verbindung mit `let` dem-Schlüsselwort verwendet, um eine rekursive Funktion zu definieren.</span><span class="sxs-lookup"><span data-stu-id="64d2d-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="64d2d-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="64d2d-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="64d2d-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="64d2d-106">Remarks</span></span>

<span data-ttu-id="64d2d-107">Rekursive Funktionen, Funktionen, die selbst aufrufen, werden in der Sprache F# explizit identifiziert.</span><span class="sxs-lookup"><span data-stu-id="64d2d-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="64d2d-108">Dadurch ist der zu definierenden identierer im Gültigkeitsbereich der Funktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="64d2d-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="64d2d-109">Der folgende Code veranschaulicht eine rekursive Funktion, die die *n*<sup></sup> -te "fbonacci"-Zahl berechnet.</span><span class="sxs-lookup"><span data-stu-id="64d2d-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="64d2d-110">In der Praxis ist der oben genannte Code verschwenderisch für Arbeitsspeicher und Prozessorzeit, da er die Neuberechnung der zuvor berechneten Werte einschließt.</span><span class="sxs-lookup"><span data-stu-id="64d2d-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="64d2d-111">Methoden sind implizit rekursiv innerhalb des Typs. Es ist nicht erforderlich, das `rec` -Schlüsselwort hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="64d2d-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="64d2d-112">Let-Bindungen in Klassen sind nicht implizit rekursiv.</span><span class="sxs-lookup"><span data-stu-id="64d2d-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="64d2d-113">Gegenseitig rekursive Funktionen</span><span class="sxs-lookup"><span data-stu-id="64d2d-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="64d2d-114">Manchmal sind Funktionen *gegenseitig rekursiv*. Dies bedeutet, dass Aufrufe einen Kreis bilden, wobei eine Funktion eine andere aufruft, die wiederum den ersten aufruft, wobei eine beliebige Anzahl von Aufrufen dazwischen ist.</span><span class="sxs-lookup"><span data-stu-id="64d2d-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="64d2d-115">Sie müssen diese Funktionen in der eine `let` Bindung zusammen definieren, indem Sie das `and` -Schlüsselwort verwenden, um Sie miteinander zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="64d2d-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="64d2d-116">Das folgende Beispiel zeigt zwei gegenseitig rekursive Funktionen.</span><span class="sxs-lookup"><span data-stu-id="64d2d-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="64d2d-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="64d2d-117">See also</span></span>

- [<span data-ttu-id="64d2d-118">Funktionen</span><span class="sxs-lookup"><span data-stu-id="64d2d-118">Functions</span></span>](index.md)
