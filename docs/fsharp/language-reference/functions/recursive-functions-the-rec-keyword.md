---
title: 'Rekursive Funktionen: Das rec-Schlüsselwort (F#)'
description: Erfahren Sie, wie das f#-Schlüsselwort "Rec" mit dem Schlüsselwort "let" verwendet wird, um eine rekursive Funktion zu definieren.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 1f5302c125605d2186deab0bbeaf2e84cc51edc3
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="recursive-functions-the-rec-keyword"></a><span data-ttu-id="5f118-103">Rekursive Funktionen: Das rec-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="5f118-103">Recursive Functions: The rec Keyword</span></span>

<span data-ttu-id="5f118-104">Die `rec` -Schlüsselwort wird verwendet, zusammen mit den `let` Schlüsselwort, um eine rekursive Funktion definieren.</span><span class="sxs-lookup"><span data-stu-id="5f118-104">The `rec` keyword is used together with the `let` keyword to define a recursive function.</span></span>


## <a name="syntax"></a><span data-ttu-id="5f118-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="5f118-105">Syntax</span></span>

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

## <a name="remarks"></a><span data-ttu-id="5f118-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5f118-106">Remarks</span></span>
<span data-ttu-id="5f118-107">Rekursive Funktionen, Funktionen, die selbst aufrufen, werden in der Programmiersprache f# explizit identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5f118-107">Recursive functions, functions that call themselves, are identified explicitly in the F# language.</span></span> <span data-ttu-id="5f118-108">Dadurch wird den Bezeichner, der definiert wird im Gültigkeitsbereich der Funktion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5f118-108">This makes the identifer that is being defined available in the scope of the function.</span></span>

<span data-ttu-id="5f118-109">Das folgende Codebeispiel veranschaulicht eine rekursive Funktion, die berechnet die *n*te Fibonacci-Zahl.</span><span class="sxs-lookup"><span data-stu-id="5f118-109">The following code illustrates a recursive function that computes the *n*th Fibonacci number.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4001.fs)]

>[!NOTE]
<span data-ttu-id="5f118-110">In der Praxis ist wie oben angegeben Codes gehen zu Lasten der Arbeitsspeicher und Prozessorzeit, da hierbei die neuberechnung der zuvor berechnete Werte.</span><span class="sxs-lookup"><span data-stu-id="5f118-110">In practice, code like that above is wasteful of memory and processor time because it involves the recomputation of previously computed values.</span></span>


<span data-ttu-id="5f118-111">Methoden sind implizit rekursiv innerhalb des Typs. besteht keine Notwendigkeit zum Hinzufügen der `rec` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="5f118-111">Methods are implicitly recursive within the type; there is no need to add the `rec` keyword.</span></span> <span data-ttu-id="5f118-112">Let-Bindungen in Klassen sind nicht implizit rekursiv.</span><span class="sxs-lookup"><span data-stu-id="5f118-112">Let bindings within classes are not implicitly recursive.</span></span>


## <a name="mutually-recursive-functions"></a><span data-ttu-id="5f118-113">Wechselseitig rekursive Funktionen</span><span class="sxs-lookup"><span data-stu-id="5f118-113">Mutually Recursive Functions</span></span>
<span data-ttu-id="5f118-114">In einigen Fällen Funktionen sind *wechselseitig rekursive*, was bedeutet, dass Aufrufe einen Kreis bilden, in denen eine bestimmte Funktion aufruft anderen, die ihrerseits die erste Seite mit einer beliebigen Anzahl von Aufrufen zwischen.</span><span class="sxs-lookup"><span data-stu-id="5f118-114">Sometimes functions are *mutually recursive*, meaning that calls form a circle, where one function calls another which in turn calls the first, with any number of calls in between.</span></span> <span data-ttu-id="5f118-115">Müssen Sie solche Funktionen zusammen in einem definieren `let` Bindungen, mit dem `and` Schlüsselwort, um sie miteinander verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="5f118-115">You must define such functions together in the one `let` binding, using the `and` keyword to link them together.</span></span>

<span data-ttu-id="5f118-116">Das folgende Beispiel zeigt zwei wechselseitig rekursive Funktionen.</span><span class="sxs-lookup"><span data-stu-id="5f118-116">The following example shows two mutually recursive functions.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet4002.fs)]

## <a name="see-also"></a><span data-ttu-id="5f118-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5f118-117">See Also</span></span>
[<span data-ttu-id="5f118-118">Funktionen</span><span class="sxs-lookup"><span data-stu-id="5f118-118">Functions</span></span>](index.md)
