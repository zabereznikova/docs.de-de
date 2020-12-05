---
title: Slices
description: 'Erfahren Sie, wie Sie Slices für vorhandene F #-Datentypen verwenden und wie Sie eigene Slices für andere Datentypen definieren.'
ms.date: 11/20/2020
ms.openlocfilehash: b776058df5a174dfe48dbf513bf17281036dd83e
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740379"
---
# <a name="slices"></a><span data-ttu-id="94b78-103">Slices</span><span class="sxs-lookup"><span data-stu-id="94b78-103">Slices</span></span>

<span data-ttu-id="94b78-104">In diesem Artikel wird erläutert, wie Sie Slices aus vorhandenen F #-Typen erstellen und eigene Slices definieren.</span><span class="sxs-lookup"><span data-stu-id="94b78-104">This article explains how to take slices from existing F# types and how to define your own slices.</span></span>

<span data-ttu-id="94b78-105">In F # ist ein Slice eine Teilmenge eines beliebigen Datentyps.</span><span class="sxs-lookup"><span data-stu-id="94b78-105">In F#, a slice is a subset of any data type.</span></span>  <span data-ttu-id="94b78-106">Slices ähneln [Indexer](./members/indexed-properties.md), aber anstelle eines einzelnen Werts aus der zugrunde liegenden Datenstruktur ergeben sich mehrere Segmente.</span><span class="sxs-lookup"><span data-stu-id="94b78-106">Slices are similar to [indexers](./members/indexed-properties.md), but instead of yielding a single value from the underlying data structure, they yield multiple ones.</span></span> <span data-ttu-id="94b78-107">Slices verwenden die `..` Operator Syntax, um den Bereich der angegebenen Indizes in einem Datentyp auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="94b78-107">Slices use the `..` operator syntax to select the range of specified indices in a data type.</span></span> <span data-ttu-id="94b78-108">Weitere Informationen finden Sie im [Referenz Artikel zum Schleifen Ausdruck](./loops-for-in-expression.md).</span><span class="sxs-lookup"><span data-stu-id="94b78-108">For more information, see the [looping expression reference article](./loops-for-in-expression.md).</span></span>

<span data-ttu-id="94b78-109">F # verfügt zurzeit über eine intrinsische Unterstützung für das Aufteilen von Zeichen folgen, Listen, Arrays und mehrdimensionalen Arrays (2D, 3D, 4D).</span><span class="sxs-lookup"><span data-stu-id="94b78-109">F# currently has intrinsic support for slicing strings, lists, arrays, and multidimensional (2D, 3D, 4D) arrays.</span></span> <span data-ttu-id="94b78-110">Die Slicing wird am häufigsten bei F #-Arrays und-Listen verwendet.</span><span class="sxs-lookup"><span data-stu-id="94b78-110">Slicing is most commonly used with F# arrays and lists.</span></span> <span data-ttu-id="94b78-111">Sie können den benutzerdefinierten Datentypen aufteilen hinzufügen, indem Sie die- `GetSlice` Methode in ihrer Typdefinition oder in einer [Typerweiterung](type-extensions.md)im Gültigkeitsbereich verwenden.</span><span class="sxs-lookup"><span data-stu-id="94b78-111">You can add slicing to your custom data types by using the `GetSlice` method in your type definition or in an in-scope [type extension](type-extensions.md).</span></span>

## <a name="slicing-f-lists-and-arrays"></a><span data-ttu-id="94b78-112">Aufteilen von F #-Listen und-Arrays</span><span class="sxs-lookup"><span data-stu-id="94b78-112">Slicing F# lists and arrays</span></span>

<span data-ttu-id="94b78-113">Die häufigsten Datentypen, die in Slices aufgeteilt sind, sind F #-Listen und-Arrays.</span><span class="sxs-lookup"><span data-stu-id="94b78-113">The most common data types that are sliced are F# lists and arrays.</span></span>  <span data-ttu-id="94b78-114">Im folgenden Beispiel wird veranschaulicht, wie Listen aufgeteilt werden:</span><span class="sxs-lookup"><span data-stu-id="94b78-114">The following example demonstrates how to slice lists:</span></span>

```fsharp
// Generate a list of 100 integers
let fullList = [ 1 .. 100 ]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullList.[1..5]
printfn $"Small slice: {smallSlice}"

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullList.[..5]
printfn $"Unbounded beginning slice: {unboundedBeginning}"

// Create a slice from an index to the end of the list
let unboundedEnd = fullList.[94..]
printfn $"Unbounded end slice: {unboundedEnd}"
```

<span data-ttu-id="94b78-115">Das Aufteilen von Arrays ist ebenso wie das Aufteilen von Listen:</span><span class="sxs-lookup"><span data-stu-id="94b78-115">Slicing arrays is just like slicing lists:</span></span>

```fsharp
// Generate an array of 100 integers
let fullArray = [| 1 .. 100 |]

// Create a slice from indices 1-5 (inclusive)
let smallSlice = fullArray.[1..5]
printfn $"Small slice: {smallSlice}"

// Create a slice from the beginning to index 5 (inclusive)
let unboundedBeginning = fullArray.[..5]
printfn $"Unbounded beginning slice: {unboundedBeginning}"

// Create a slice from an index to the end of the list
let unboundedEnd = fullArray.[94..]
printfn $"Unbounded end slice: {unboundedEnd}"
```

## <a name="slicing-multidimensional-arrays"></a><span data-ttu-id="94b78-116">Aufteilen von mehrdimensionalen Arrays</span><span class="sxs-lookup"><span data-stu-id="94b78-116">Slicing multidimensional arrays</span></span>

<span data-ttu-id="94b78-117">F # unterstützt mehrdimensionale Arrays in der F #-Kernbibliothek.</span><span class="sxs-lookup"><span data-stu-id="94b78-117">F# supports multidimensional arrays in the F# core library.</span></span> <span data-ttu-id="94b78-118">Wie bei eindimensionalen Arrays können auch Slices von mehrdimensionalen Arrays nützlich sein.</span><span class="sxs-lookup"><span data-stu-id="94b78-118">As with one-dimensional arrays, slices of multidimensional arrays can also be useful.</span></span> <span data-ttu-id="94b78-119">Die Einführung zusätzlicher Dimensionen erfordert jedoch eine etwas andere Syntax, sodass Sie Slices bestimmter Zeilen und Spalten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="94b78-119">However, the introduction of additional dimensions mandates a slightly different syntax so that you can take slices of specific rows and columns.</span></span>

<span data-ttu-id="94b78-120">In den folgenden Beispielen wird veranschaulicht, wie Sie ein 2D-Array in einen Slice</span><span class="sxs-lookup"><span data-stu-id="94b78-120">The following examples demonstrate how to slice a 2D array:</span></span>

```fsharp
// Generate a 3x3 2D matrix
let A = array2D [[1;2;3];[4;5;6];[7;8;9]]
printfn $"Full matrix:\n {A}"

// Take the first row
let row0 = A.[0,*]
printfn $"{row0}"

// Take the first column
let col0 = A.[*,0]
printfn $"{col0}"

// Take all rows but only two columns
let subA = A.[*,0..1]
printfn $"{subA}"

// Take two rows and all columns
let subA' = A.[0..1,*]
printfn $"{subA}"

// Slice a 2x2 matrix out of the full 3x3 matrix
let twoByTwo = A.[0..1,0..1]
printfn $"{twoByTwo}"
```

## <a name="defining-slices-for-other-data-structures"></a><span data-ttu-id="94b78-121">Definieren von Slices für andere Datenstrukturen</span><span class="sxs-lookup"><span data-stu-id="94b78-121">Defining slices for other data structures</span></span>

<span data-ttu-id="94b78-122">Die F #-Kernbibliothek definiert Slices für einen begrenzten Satz von Typen.</span><span class="sxs-lookup"><span data-stu-id="94b78-122">The F# core library defines slices for a limited set of types.</span></span> <span data-ttu-id="94b78-123">Wenn Sie Slices für weitere Datentypen definieren möchten, können Sie dies entweder in der Typdefinition selbst oder in einer Typerweiterung tun.</span><span class="sxs-lookup"><span data-stu-id="94b78-123">If you wish to define slices for more data types, you can do so either in the type definition itself or in a type extension.</span></span>

<span data-ttu-id="94b78-124">So können Sie z. b. Slices für die- <xref:System.ArraySegment%601> Klasse definieren, um eine bequeme Datenbearbeitung zu ermöglichen:</span><span class="sxs-lookup"><span data-stu-id="94b78-124">For example, here's how you might define slices for the <xref:System.ArraySegment%601> class to allow for convenient data manipulation:</span></span>

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

<span data-ttu-id="94b78-125">Ein weiteres Beispiel, in dem die <xref:System.Span%601> Typen und verwendet werden <xref:System.ReadOnlySpan%601> :</span><span class="sxs-lookup"><span data-stu-id="94b78-125">Another example using the <xref:System.Span%601> and <xref:System.ReadOnlySpan%601> types:</span></span>

```fsharp
open System

type ReadOnlySpan<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

type Span<'T> with
    member sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e - s)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn $"{arr}"

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..3] // |2; 3|]
```

## <a name="built-in-f-slices-are-end-inclusive"></a><span data-ttu-id="94b78-126">Integrierte F #-Slices sind End-inclusive</span><span class="sxs-lookup"><span data-stu-id="94b78-126">Built-in F# slices are end-inclusive</span></span>

<span data-ttu-id="94b78-127">Alle systeminternen Slices in F # sind End-inclusive. Das heißt, die obere Grenze ist im Slice enthalten.</span><span class="sxs-lookup"><span data-stu-id="94b78-127">All intrinsic slices in F# are end-inclusive; that is, the upper bound is included in the slice.</span></span> <span data-ttu-id="94b78-128">Für ein bestimmtes Slice mit dem Start Index `x` und dem endIndex `y` enthält der resultierende Slice den Wert *YTH* .</span><span class="sxs-lookup"><span data-stu-id="94b78-128">For a given slice with starting index `x` and ending index `y`, the resulting slice will include the *yth* value.</span></span>

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn $"{xs.[2..5]}" // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a><span data-ttu-id="94b78-129">Integrierte F #-Slices</span><span class="sxs-lookup"><span data-stu-id="94b78-129">Built-in F# empty slices</span></span>

<span data-ttu-id="94b78-130">F #-Listen, Arrays, Sequenzen, Zeichen folgen, mehrdimensionale (2D, 3D, 4D) Arrays erzeugen ein leeres Slice, wenn die Syntax einen Slice erzeugen könnte, der nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="94b78-130">F# lists, arrays, sequences, strings, multidimensional (2D, 3D, 4D) arrays will all produce an empty slice if the syntax could produce a slice that doesn't exist.</span></span>

<span data-ttu-id="94b78-131">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="94b78-131">Consider the following example:</span></span>

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

> [!IMPORTANT]
> <span data-ttu-id="94b78-132">C#-Entwickler erwarten möglicherweise, dass diese eine Ausnahme auslösen, anstatt einen leeren Slice zu liefern.</span><span class="sxs-lookup"><span data-stu-id="94b78-132">C# developers may expect these to throw an exception rather than produce an empty slice.</span></span> <span data-ttu-id="94b78-133">Dies ist eine Entwurfs Entscheidung, die auf die Tatsache beruht, dass leere Auflistungen in F # verfasst werden.</span><span class="sxs-lookup"><span data-stu-id="94b78-133">This is a design decision rooted in the fact that empty collections compose in F#.</span></span> <span data-ttu-id="94b78-134">Eine leere f #-Liste kann mit einer anderen f #-Liste zusammengesetzt werden, eine leere Zeichenfolge kann einer vorhandenen Zeichenfolge hinzugefügt werden usw.</span><span class="sxs-lookup"><span data-stu-id="94b78-134">An empty F# list can be composed with another F# list, an empty string can be added to an existing string, and so on.</span></span> <span data-ttu-id="94b78-135">Es kann üblich sein, Slices auf der Grundlage von Werten zu verwenden, die als Parameter weitergegeben werden, und die Toleranz außerhalb der Grenzen > durch die Erstellung einer leeren Auflistung, die mit der kompositorischen Natur von F #-Code zu erreichen ist.</span><span class="sxs-lookup"><span data-stu-id="94b78-135">It can be common to take slices based on values passed in as parameters, and being tolerant of out-of-bounds > by producing an empty collection fits with the compositional nature of F# code.</span></span>

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a><span data-ttu-id="94b78-136">Blöcke mit fester Indexgröße für 3D-und 4D-Arrays</span><span class="sxs-lookup"><span data-stu-id="94b78-136">Fixed-index slices for 3D and 4D arrays</span></span>

<span data-ttu-id="94b78-137">Bei F #-3D-und 4D-Arrays können Sie einen bestimmten Index "korrigieren" und andere Dimensionen mit fester Größe in einem Slice teilen.</span><span class="sxs-lookup"><span data-stu-id="94b78-137">For F# 3D and 4D arrays, you can "fix" a particular index and slice other dimensions with that index fixed.</span></span>

<span data-ttu-id="94b78-138">Um dies zu veranschaulichen, sehen Sie sich das folgende 3D-Array an:</span><span class="sxs-lookup"><span data-stu-id="94b78-138">To illustrate this, consider the following 3D array:</span></span>

<span data-ttu-id="94b78-139">*z = 0*</span><span class="sxs-lookup"><span data-stu-id="94b78-139">*z = 0*</span></span>

| <span data-ttu-id="94b78-140">x\y</span><span class="sxs-lookup"><span data-stu-id="94b78-140">x\y</span></span>   | <span data-ttu-id="94b78-141">0</span><span class="sxs-lookup"><span data-stu-id="94b78-141">0</span></span> | <span data-ttu-id="94b78-142">1</span><span class="sxs-lookup"><span data-stu-id="94b78-142">1</span></span> |
|-------|---|---|
| <span data-ttu-id="94b78-143">**0**</span><span class="sxs-lookup"><span data-stu-id="94b78-143">**0**</span></span> | <span data-ttu-id="94b78-144">0</span><span class="sxs-lookup"><span data-stu-id="94b78-144">0</span></span> | <span data-ttu-id="94b78-145">1</span><span class="sxs-lookup"><span data-stu-id="94b78-145">1</span></span> |
| <span data-ttu-id="94b78-146">**1**</span><span class="sxs-lookup"><span data-stu-id="94b78-146">**1**</span></span> | <span data-ttu-id="94b78-147">2</span><span class="sxs-lookup"><span data-stu-id="94b78-147">2</span></span> | <span data-ttu-id="94b78-148">3</span><span class="sxs-lookup"><span data-stu-id="94b78-148">3</span></span> |

<span data-ttu-id="94b78-149">*z = 1*</span><span class="sxs-lookup"><span data-stu-id="94b78-149">*z = 1*</span></span>

| <span data-ttu-id="94b78-150">x\y</span><span class="sxs-lookup"><span data-stu-id="94b78-150">x\y</span></span>   | <span data-ttu-id="94b78-151">0</span><span class="sxs-lookup"><span data-stu-id="94b78-151">0</span></span> | <span data-ttu-id="94b78-152">1</span><span class="sxs-lookup"><span data-stu-id="94b78-152">1</span></span> |
|-------|---|---|
| <span data-ttu-id="94b78-153">**0**</span><span class="sxs-lookup"><span data-stu-id="94b78-153">**0**</span></span> | <span data-ttu-id="94b78-154">4</span><span class="sxs-lookup"><span data-stu-id="94b78-154">4</span></span> | <span data-ttu-id="94b78-155">5</span><span class="sxs-lookup"><span data-stu-id="94b78-155">5</span></span> |
| <span data-ttu-id="94b78-156">**1**</span><span class="sxs-lookup"><span data-stu-id="94b78-156">**1**</span></span> | <span data-ttu-id="94b78-157">6</span><span class="sxs-lookup"><span data-stu-id="94b78-157">6</span></span> | <span data-ttu-id="94b78-158">7</span><span class="sxs-lookup"><span data-stu-id="94b78-158">7</span></span> |

<span data-ttu-id="94b78-159">Wenn Sie den Slice `[| 4; 5 |]` aus dem Array extrahieren möchten, verwenden Sie einen Slice mit fester Indexgröße.</span><span class="sxs-lookup"><span data-stu-id="94b78-159">If you want to extract the slice `[| 4; 5 |]` from the array, use a fixed-index slice.</span></span>

```fsharp
let dim = 2
let m = Array3D.zeroCreate<int> dim dim dim

let mutable count = 0

for z in 0..dim-1 do
    for y in 0..dim-1 do
        for x in 0..dim-1 do
            m.[x,y,z] <- count
            count <- count + 1

// Now let's get the [4;5] slice!
m.[*, 0, 1]
```

<span data-ttu-id="94b78-160">Die letzte Zeile korrigiert die `y` `z` Indizes und des 3D-Arrays und übernimmt die restlichen `x` Werte, die der Matrix entsprechen.</span><span class="sxs-lookup"><span data-stu-id="94b78-160">The last line fixes the `y` and `z` indices of the 3D array and takes the rest of the `x` values that correspond to the matrix.</span></span>

## <a name="see-also"></a><span data-ttu-id="94b78-161">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="94b78-161">See also</span></span>

- [<span data-ttu-id="94b78-162">Indizierte Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="94b78-162">Indexed properties</span></span>](./members/indexed-properties.md)
