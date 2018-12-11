---
title: 'Rekursive Funktionen: Das Rec-Schlüsselwort (F#)'
description: Erfahren Sie, wie die F# 'Rec'-Schlüsselwort wird mit dem Schlüsselwort "let" verwendet, um eine rekursive Funktion zu definieren.
ms.date: 05/16/2016
ms.openlocfilehash: 0db3ed7f85a1380654f2827b4773985b661589c7
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53127731"
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="73060-103">Rekursive Funktionen: Das Rec-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="73060-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="73060-104">Die `rec` -Schlüsselwort wird verwendet, zusammen mit den `let` Schlüsselwort, um eine rekursive Funktion zu definieren.</span><span class="sxs-lookup"><span data-stu-id="73060-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>

## <a name="syntax"></a><span data-ttu-id="73060-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="73060-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="73060-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="73060-106">Remarks</span></span>

<span data-ttu-id="73060-107">Rekursive Funktionen, Funktionen, die selbst aufrufen, werden in der Sprache F# explizit identifiziert.</span><span class="sxs-lookup"><span data-stu-id="73060-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="73060-108">Dadurch wird den Bezeichner, der definiert wird im Rahmen der Funktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="73060-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="73060-109">Der folgende Code zeigt eine rekursive Funktion, die berechnet die *n*<sup>th</sup> Fibonacci-Zahl.</span><span class="sxs-lookup"><span data-stu-id="73060-109">The following code illustrates a recursive function that computes the *n*<sup>th</sup> Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

> [!NOTE]
> <span data-ttu-id="73060-110">Genauso wie der obige Code ist in der Praxis gehen zu Lasten der Arbeitsspeicher und Prozessorzeit, da hierbei die neuberechnung der zuvor berechnete Werte.</span><span class="sxs-lookup"><span data-stu-id="73060-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>

<span data-ttu-id="73060-111">Methoden sind implizit rekursiv innerhalb des Typs. besteht keine Notwendigkeit zum Hinzufügen der `rec` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="73060-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="73060-112">Let-Bindungen in Klassen sind nicht implizit rekursiv.</span><span class="sxs-lookup"><span data-stu-id="73060-112">Let bindings within classes are not implicitly recursive.</span></span>

## <a name="mutually-recursive-functions"></a><span data-ttu-id="73060-113">Wechselseitig rekursive Funktionen</span><span class="sxs-lookup"><span data-stu-id="73060-113">Mutually Recursive Functions</span></span>

<span data-ttu-id="73060-114">Funktionen in einigen Fällen sind *wechselseitig rekursive*, was bedeutet, dass Aufrufe einen Kreis zu bilden, in dem eine Funktion aufruft, eine andere der aufruft, die erste, wiederum mit einer beliebigen Anzahl von Aufrufen zwischen.</span><span class="sxs-lookup"><span data-stu-id="73060-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="73060-115">Müssen Sie solche Funktionen zusammen definieren, die `let` binden, unter Verwendung der `and` Schlüsselwort, um sie miteinander verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="73060-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="73060-116">Das folgende Beispiel zeigt zwei sich gegenseitig rekursiver Funktionen.</span><span class="sxs-lookup"><span data-stu-id="73060-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="73060-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="73060-117">See also</span></span>

- [<span data-ttu-id="73060-118">Funktionen</span><span class="sxs-lookup"><span data-stu-id="73060-118">Functions</span></span>](index.md)
