---
title: Slices
description: Erfahren Sie, wie Sie Slices für F# vorhandene Datentypen verwenden und eigene Slices für andere Datentypen definieren.
ms.date: 12/23/2019
ms.openlocfilehash: 3911139c7ce656043817eb23d30f3686555b6efe
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545105"
---
# <a name="slices"></a>Slices

In F#handelt es sich bei einem Slice um eine Teilmenge eines beliebigen Datentyps, der über eine `GetSlice`-Methode in seiner Definition oder eine in-Scope- [Typerweiterung](type-extensions.md)verfügt. Es wird am häufigsten mit F# Arrays und Listen verwendet. In diesem Artikel wird erläutert, wie Sie Slices F# aus vorhandenen Typen erstellen und eigene Slices definieren.

Slices ähneln [Indexer](./members/indexed-properties.md), aber anstelle eines einzelnen Werts aus der zugrunde liegenden Datenstruktur ergeben sich mehrere Segmente.

F#bietet derzeit eine intrinsische Unterstützung für das Aufteilen von Zeichen folgen, Listen, Arrays und 2D-Arrays.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>Einfache aufteilen mit F# Listen und Arrays

Die häufigsten Datentypen, die in Slices aufgeteilt F# sind, sind Listen und Arrays. Im folgenden Beispiel wird die Vorgehensweise mit Listen veranschaulicht:

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

Das Aufteilen von Arrays ist ebenso wie das Aufteilen von Listen:

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

## <a name="slicing-multidimensional-arrays"></a>Aufteilen von mehrdimensionalen Arrays

F#unterstützt mehrdimensionale Arrays F# in der Kernbibliothek. Wie bei eindimensionalen Arrays können auch Slices von mehrdimensionalen Arrays nützlich sein. Die Einführung zusätzlicher Dimensionen erfordert jedoch eine etwas andere Syntax, sodass Sie Slices bestimmter Zeilen und Spalten verwenden können.

In den folgenden Beispielen wird veranschaulicht, wie Sie ein 2D-Array in einen Slice

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

In F# der Kernbibliothek wird derzeit nicht `GetSlice` für 3D-Arrays definiert. Wenn Sie 3D-Arrays oder andere Arrays von mehr Dimensionen segmentieren möchten, definieren Sie das `GetSlice` Member selbst.

## <a name="defining-slices-for-other-data-structures"></a>Definieren von Slices für andere Datenstrukturen

Die F# Core-Bibliothek definiert Slices für einen begrenzten Satz von Typen. Wenn Sie Slices für weitere Datentypen definieren möchten, können Sie dies entweder in der Typdefinition selbst oder in einer Typerweiterung tun.

So können Sie z. b. Slices für die <xref:System.ArraySegment%601>-Klasse definieren, um eine bequeme Datenbearbeitung zu ermöglichen:

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

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>Verwenden Sie Inlining, um bei Bedarf Boxing zu vermeiden.

Wenn Sie Slices für einen Typ definieren, der eigentlich eine Struktur ist, wird empfohlen, dass Sie den `GetSlice` Member `inline`. Der F# Compiler optimiert die optionalen Argumente, wobei Heap Zuordnungen aufgrund der slizierung vermieden werden. Dies ist für aufteilen-Konstrukte, z. b. <xref:System.Span%601>, die nicht auf dem Heap zugeordnet werden können, äußerst wichtig.

```fsharp
open System

type ReadOnlySpan<'T> with
    // Note the 'inline' in the member definition
    member sp.GetSlice(startIdx, endIdx) =
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

## <a name="built-in-f-slices-are-end-inclusive"></a>Integrierte F# Slices sind End-inclusive

Alle systeminternen Slices F# in sind End-inclusive. Das heißt, die obere Grenze ist im Slice enthalten. Für ein bestimmtes Slice mit Start Index `x` und dem endIndex `y`enthält der resultierende Slice den Wert *YTH* .

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn "%A" xs.[2..5] // Includes the 5th index
```

## <a name="see-also"></a>Siehe auch

- [Indizierte Eigenschaften](./members/indexed-properties.md)
