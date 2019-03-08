---
title: Slices (F#)
description: Erfahren Sie, wie Sie mit Slices für bestehende F# -Datentypen und wie Sie Ihre eigenen Slices für andere Datentypen zu definieren.
ms.date: 01/22/2019
ms.openlocfilehash: 1d8bb029ad18c8853ab58888959967ed279fb368
ms.sourcegitcommit: 58fc0e6564a37fa1b9b1b140a637e864c4cf696e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/08/2019
ms.locfileid: "57675276"
---
# <a name="slices"></a>Slices

In F#, ein Slice ist eine Teilmenge von einem Datentyp. Um einen Slice von einem Datentyp werden können, der Datentyp muss entweder definieren eine `GetSlice` Methode oder in eine ["Erweiterung"](type-extensions.md) , im Bereich. In diesem Artikel wird erläutert, wie Slices aus vorhandenen F# Typen und wie Sie Ihre eigenen definieren.

Slices ähneln [Indexer](members/indexed-properties.md), jedoch anstelle der Rückgabe eines einzelnen Werts aus der zugrunde liegende Datenstruktur, mehrere zu.

F#derzeit verfügt über systeminterne Unterstützung für das Aufteilen von Zeichenfolgen, Listen, Arrays und Direct2D-Arrays.

## <a name="basic-slicing-with-f-lists-and-arrays"></a>Grundlegende Aufteilen in Slices mit F# Listen und Arrays

Die am häufigsten verwendeten Datentypen, die in Slices aufgeteilt werden sind F# Listen und Arrays. Im folgenden wird veranschaulicht, wie Sie dies mit Listen:

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

Aufteilen in Slices Arrays ist, genau wie das Aufteilen in Slices aufgelistet:

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

## <a name="slicing-multidimensional-arrays"></a>Segmentieren von mehrdimensionalen arrays

F#mehrdimensionale Arrays in unterstützt die F# -Kernbibliothek. Wie bei eindimensionalen Arrays können Segmente der mehrdimensionalen Arrays auch nützlich sein. Allerdings erfordert die Einführung von zusätzliche Dimensionen eine etwas andere Syntax, damit Sie die Slices von bestimmten Zeilen und Spalten nutzen können.

Die folgenden Beispiele veranschaulichen, wie Sie einem 2D-Array unterteilen:

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

Die F# Core-Bibliothek definiert keine `GetSlice`für 3D Arrays. Wenn Sie diese oder andere Arrays mit mehr Dimensionen in Slices aufteilen möchten, müssen Sie definieren die `GetSlice` Element selbst.

## <a name="defining-slices-for-other-data-structures"></a>Definieren von Slices für andere Datenstrukturen

Die F# Segmente für einen begrenzten Satz von Typen definiert. Wenn Sie die Slices für mehr Datentypen definieren möchten, können Sie entweder in die Typdefinition selbst oder in einer typerweiterung dafür.

Beispielsweise sieht wie Sie die Slices für definieren können die <xref:System.ArraySegment%601> Klasse, um die einfache datenbearbeitung zu ermöglichen:

```fsharp
open System

type ArraySegment<'TItem> with
    member segment.GetSlice(?start, ?finish) =
        let start = defaultArg start 0
        let finish = defaultArg finish segment.Count
        ArraySegment(segment.Array, segment.Offset + start, finish - start)

let arr = ArraySegment [| 1 .. 10 |]
let slice = arr.[2..5] //[ 3; 4; 5]
```

### <a name="use-inlining-to-avoid-boxing-if-it-is-necessary"></a>Um Boxing zu vermeiden, sollte es nötig inlining verwenden

Wenn Sie Segmente für einen Typ, die tatsächlich eine Struktur ist definieren, wird empfohlen, die Sie `inline` der `GetSlice` Member. Die F# Compiler optimiert die optionalen Argumente, die jegliche Heapzuweisungen durch das Aufteilen in Slices zu vermeiden. Dies ist sehr wichtig für das Segmentieren von Konstrukten wie z. B. <xref:System.Span%601> , die nicht auf dem Heap zugeordnet werden können.

```fsharp
open System

type Span<'T> with
    // Note the 'inline' in the member definition
    member inline sp.GetSlice(startIdx, endIdx) =
        let s = defaultArg startIdx 0
        let e = defaultArg endIdx sp.Length
        sp.Slice(s, e)

let printSpan (sp: Span<int>) =
    let arr = sp.ToArray()
    printfn "%A" arr

let sp = [| 1; 2; 3; 4; 5 |].AsSpan()
printSpan sp.[0..] // [|1; 2; 3; 4; 5|]
printSpan sp.[..5] // [|1; 2; 3; 4; 5|]
printSpan sp.[0..3] // [|1; 2; 3|]
printSpan sp.[1..2] // |2; 3|]
```

## <a name="see-also"></a>Siehe auch

- [Indizierte Eigenschaften](members/indexed-properties.md)
