---
title: "Rekursive Funktionen: Das rec-Schlüsselwort (F#)"
description: "Erfahren Sie, wie das f#-Schlüsselwort \"Rec\" mit dem Schlüsselwort \"let\" verwendet wird, um eine rekursive Funktion zu definieren."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 1a95639f-9bfe-4f1d-a5e2-246d1d37776e
ms.openlocfilehash: b837d2c0f8e2b1d28980620103097ccc8345c098
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="e66a8-104">Rekursive Funktionen: Das rec-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="e66a8-104">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="e66a8-105">Die `rec` -Schlüsselwort wird verwendet, zusammen mit den `let` Schlüsselwort, um eine rekursive Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="e66a8-105">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>


## <a name="syntax"></a><span data-ttu-id="e66a8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="e66a8-106">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="e66a8-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e66a8-107">Remarks</span></span>
<span data-ttu-id="e66a8-108">Rekursive Funktionen, Funktionen, die selbst aufrufen, werden in der Programmiersprache f# explizit identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e66a8-108">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="e66a8-109">Dadurch wird den Bezeichner, der definiert wird im Gültigkeitsbereich der Funktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e66a8-109">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="e66a8-110">Das folgende Codebeispiel veranschaulicht eine rekursive Funktion, die berechnet die  *n* te Fibonacci-Zahl.</span><span class="sxs-lookup"><span data-stu-id="e66a8-110">The following code illustrates a recursive function that computes the *n*th Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="e66a8-111">In der Praxis ist wie oben angegeben Codes gehen zu Lasten der Arbeitsspeicher und Prozessorzeit, da hierbei die neuberechnung der zuvor berechnete Werte.</span><span class="sxs-lookup"><span data-stu-id="e66a8-111">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>


<span data-ttu-id="e66a8-112">Methoden sind implizit rekursiv innerhalb des Typs. besteht keine Notwendigkeit zum Hinzufügen der `rec` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="e66a8-112">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="e66a8-113">Let-Bindungen in Klassen sind nicht implizit rekursiv.</span><span class="sxs-lookup"><span data-stu-id="e66a8-113">Let bindings within classes are not implicitly recursive.</span></span>


## <a name="mutually-recursive-functions"></a><span data-ttu-id="e66a8-114">Wechselseitig rekursive Funktionen</span><span class="sxs-lookup"><span data-stu-id="e66a8-114">Mutually Recursive Functions</span></span>
<span data-ttu-id="e66a8-115">In einigen Fällen Funktionen sind *wechselseitig rekursive*, was bedeutet, dass Aufrufe einen Kreis bilden, in denen eine bestimmte Funktion aufruft anderen, die ihrerseits die erste Seite mit einer beliebigen Anzahl von Aufrufen zwischen.</span><span class="sxs-lookup"><span data-stu-id="e66a8-115">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="e66a8-116">Müssen Sie solche Funktionen zusammen in einem definieren `let` Bindungen, mit dem `and` Schlüsselwort, um sie miteinander verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="e66a8-116">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="e66a8-117">Das folgende Beispiel zeigt zwei wechselseitig rekursive Funktionen.</span><span class="sxs-lookup"><span data-stu-id="e66a8-117">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="e66a8-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e66a8-118">See Also</span></span>
[<span data-ttu-id="e66a8-119">Funktionen</span><span class="sxs-lookup"><span data-stu-id="e66a8-119">Functions</span></span>](index.md)
