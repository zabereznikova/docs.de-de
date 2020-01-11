---
title: Slices
description: Erfahren Sie, wie Sie Slices für F# vorhandene Datentypen verwenden und eigene Slices für andere Datentypen definieren.
ms.date: 12/23/2019
ms.openlocfilehash: 3f16c71b071bab7de5b1fb90a2075e351e83cfb4
ms.sourcegitcommit: 7088f87e9a7da144266135f4b2397e611cf0a228
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2020
ms.locfileid: "75901244"
---
# <a name="slices"></a><span data-ttu-id="5bcb2-103">Slices</span><span class="sxs-lookup"><span data-stu-id="5bcb2-103">Slices</span></span>

<span data-ttu-id="5bcb2-104">In F#handelt es sich bei einem Slice um eine Teilmenge eines beliebigen Datentyps, der über eine `GetSlice`-Methode in seiner Definition oder eine in-Scope- [Typerweiterung](type-extensions.md)verfügt.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-104">In F#, a slice is a subset of any data type that has a `GetSlice` method in its definition or in an in-scope [type extension](type-extensions.md).</span></span> <span data-ttu-id="5bcb2-105">Es wird am häufigsten mit F# Arrays und Listen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-105">It is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="5bcb2-106">In diesem Artikel wird erläutert, wie Sie Slices F# aus vorhandenen Typen erstellen und eigene Slices definieren.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-106">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="5bcb2-107">Slices ähneln [Indexer](./members/indexed-properties.md), aber anstelle eines einzelnen Werts aus der zugrunde liegenden Datenstruktur ergeben sich mehrere Segmente.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-107">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span>

<span data-ttu-id="5bcb2-108">F#bietet derzeit eine intrinsische Unterstützung für das Aufteilen von Zeichen folgen, Listen, Arrays und 2D-Arrays.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-108">F# currently has intrinsic support for slicing strings, lists, arrays, and 2D arrays.</span></span>

## <a name="basic-slicing-with-f-lists-and-arrays"></a><span data-ttu-id="5bcb2-109">Einfache aufteilen mit F# Listen und Arrays</span><span class="sxs-lookup"><span data-stu-id="5bcb2-109">Basic slicing with F# lists and arrays</span></span>

<span data-ttu-id="5bcb2-110">Die häufigsten Datentypen, die in Slices aufgeteilt F# sind, sind Listen und Arrays.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-110">The most common data types that are sliced are F# lists and arrays.</span></span> <span data-ttu-id="5bcb2-111">Im folgenden Beispiel wird die Vorgehensweise mit Listen veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5bcb2-111">The following example demonstrates how to do this with lists:</span></span>

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

<span data-ttu-id="5bcb2-112">Das Aufteilen von Arrays ist ebenso wie das Aufteilen von Listen:</span><span class="sxs-lookup"><span data-stu-id="5bcb2-112">Slicing arrays is just like slicing lists:</span></span>

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn "Small slice: %A" smallSlice

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn "Unbounded beginning slice: %A" unboundedBeginning

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn "Unbounded end slice: %A" unboundedEnd
```

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="5bcb2-113">Aufteilen von mehrdimensionalen Arrays</span><span class="sxs-lookup"><span data-stu-id="5bcb2-113">Slicing multidimensional arrays</span></span>

<span data-ttu-id="5bcb2-114">F#unterstützt mehrdimensionale Arrays F# in der Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-114">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="5bcb2-115">Wie bei eindimensionalen Arrays können auch Slices von mehrdimensionalen Arrays nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-115">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="5bcb2-116">Die Einführung zusätzlicher Dimensionen erfordert jedoch eine etwas andere Syntax, sodass Sie Slices bestimmter Zeilen und Spalten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-116">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="5bcb2-117">In den folgenden Beispielen wird veranschaulicht, wie Sie ein 2D-Array in einen Slice</span><span class="sxs-lookup"><span data-stu-id="5bcb2-117">The following examples demonstrate how to slice a 2D array:</span></span>

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn "Full matrix:\n %A" A

// Take the first row
let row0 = A.[0,*]
printfn "Row 0: %A" row0

// Take the first column
let col0 = A.[*,0]
printfn "Column 0: %A" col0

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn "%A" subA

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn "%A" subA'

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn "%A" twoByTwo
```

<span data-ttu-id="5bcb2-118">In F# der Kernbibliothek wird derzeit nicht `GetSlice` für 3D-Arrays definiert.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-118">The F# core library does not currently define `GetSlice` for 3D arrays.</span></span> <span data-ttu-id="5bcb2-119">Wenn Sie 3D-Arrays oder andere Arrays von mehr Dimensionen segmentieren möchten, definieren Sie das `GetSlice` Member selbst.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-119">If you wish to slice 3D arrays or other arrays of more dimensions, define the `GetSlice` member yourself.</span></span>

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="5bcb2-120">Definieren von Slices für andere Datenstrukturen</span><span class="sxs-lookup"><span data-stu-id="5bcb2-120">Defining slices for other data structures</span></span>

<span data-ttu-id="5bcb2-121">Die F# Core-Bibliothek definiert Slices für einen begrenzten Satz von Typen.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-121">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="5bcb2-122">Wenn Sie Slices für weitere Datentypen definieren möchten, können Sie dies entweder in der Typdefinition selbst oder in einer Typerweiterung tun.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-122">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="5bcb2-123">So können Sie z. b. Slices für die <xref:System.ArraySegment%601>-Klasse definieren, um eine bequeme Datenbearbeitung zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="5bcb2-123">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(start, finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a><span data-ttu-id="5bcb2-124">Verwenden Sie Inlining, um bei Bedarf Boxing zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-124">Use inlining to avoid boxing if it is necessary</span></span>

<span data-ttu-id="5bcb2-125">Wenn Sie Slices für einen Typ definieren, der eigentlich eine Struktur ist, wird empfohlen, dass Sie den `GetSlice` Member `inline`.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-125">If you are defining slices for a type that is actually a struct, we recommend that you `inline` the `GetSlice` member.</span></span> <span data-ttu-id="5bcb2-126">Der F# Compiler optimiert die optionalen Argumente, wobei Heap Zuordnungen aufgrund der slizierung vermieden werden.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-126">The F# compiler optimizes away the optional arguments, avoiding any heap allocations as a result of slicing.</span></span> <span data-ttu-id="5bcb2-127">Dies ist für aufteilen-Konstrukte, z. b. <xref:System.Span%601>, die nicht auf dem Heap zugeordnet werden können, äußerst wichtig.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-127">This is critically important for slicing constructs such as <xref:System.Span%601> that cannot be allocated on the heap.</span></span>

```fsharp
open System

type ReadOnlySpan<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="5bcb2-128">Integrierte F# Slices sind End-inclusive</span><span class="sxs-lookup"><span data-stu-id="5bcb2-128">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="5bcb2-129">Alle systeminternen Slices F# in sind End-inclusive. Das heißt, die obere Grenze ist im Slice enthalten.</span><span class="sxs-lookup"><span data-stu-id="5bcb2-129">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="5bcb2-130">Für ein bestimmtes Slice mit Start Index `x` und dem endIndex `y`enthält der resultierende Slice den Wert *YTH* .</span><span class="sxs-lookup"><span data-stu-id="5bcb2-130">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a><span data-ttu-id="5bcb2-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5bcb2-131">See also</span></span>

- [<span data-ttu-id="5bcb2-132">Indizierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="5bcb2-132">Indexed properties</span></span>](./members/indexed-properties.md)
