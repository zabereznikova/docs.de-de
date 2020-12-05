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
# <a name="slices"></a>Slices

In diesem Artikel wird erläutert, wie Sie Slices aus vorhandenen F #-Typen erstellen und eigene Slices definieren.

In F # ist ein Slice eine Teilmenge eines beliebigen Datentyps.  Slices ähneln [Indexer](./members/indexed-properties.md), aber anstelle eines einzelnen Werts aus der zugrunde liegenden Datenstruktur ergeben sich mehrere Segmente. Slices verwenden die `..` Operator Syntax, um den Bereich der angegebenen Indizes in einem Datentyp auszuwählen. Weitere Informationen finden Sie im [Referenz Artikel zum Schleifen Ausdruck](./loops-for-in-expression.md).

F # verfügt zurzeit über eine intrinsische Unterstützung für das Aufteilen von Zeichen folgen, Listen, Arrays und mehrdimensionalen Arrays (2D, 3D, 4D). Die Slicing wird am häufigsten bei F #-Arrays und-Listen verwendet. Sie können den benutzerdefinierten Datentypen aufteilen hinzufügen, indem Sie die- `GetSlice` Methode in ihrer Typdefinition oder in einer [Typerweiterung](type-extensions.md)im Gültigkeitsbereich verwenden.

## <a name="slicing-f-lists-and-arrays"></a>Aufteilen von F #-Listen und-Arrays

Die häufigsten Datentypen, die in Slices aufgeteilt sind, sind F #-Listen und-Arrays.  Im folgenden Beispiel wird veranschaulicht, wie Listen aufgeteilt werden:

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

Das Aufteilen von Arrays ist ebenso wie das Aufteilen von Listen:

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

## <a name="slicing-multidimensional-arrays"></a>Aufteilen von mehrdimensionalen Arrays

F # unterstützt mehrdimensionale Arrays in der F #-Kernbibliothek. Wie bei eindimensionalen Arrays können auch Slices von mehrdimensionalen Arrays nützlich sein. Die Einführung zusätzlicher Dimensionen erfordert jedoch eine etwas andere Syntax, sodass Sie Slices bestimmter Zeilen und Spalten verwenden können.

In den folgenden Beispielen wird veranschaulicht, wie Sie ein 2D-Array in einen Slice

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

## <a name="defining-slices-for-other-data-structures"></a>Definieren von Slices für andere Datenstrukturen

Die F #-Kernbibliothek definiert Slices für einen begrenzten Satz von Typen. Wenn Sie Slices für weitere Datentypen definieren möchten, können Sie dies entweder in der Typdefinition selbst oder in einer Typerweiterung tun.

So können Sie z. b. Slices für die- <xref:System.ArraySegment%601> Klasse definieren, um eine bequeme Datenbearbeitung zu ermöglichen:

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

Ein weiteres Beispiel, in dem die <xref:System.Span%601> Typen und verwendet werden <xref:System.ReadOnlySpan%601> :

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

## <a name="built-in-f-slices-are-end-inclusive"></a>Integrierte F #-Slices sind End-inclusive

Alle systeminternen Slices in F # sind End-inclusive. Das heißt, die obere Grenze ist im Slice enthalten. Für ein bestimmtes Slice mit dem Start Index `x` und dem endIndex `y` enthält der resultierende Slice den Wert *YTH* .

```fsharp
// Define a new list
let xs = [1 .. 10]

printfn $"{xs.[2..5]}" // Includes the 5th index
```

## <a name="built-in-f-empty-slices"></a>Integrierte F #-Slices

F #-Listen, Arrays, Sequenzen, Zeichen folgen, mehrdimensionale (2D, 3D, 4D) Arrays erzeugen ein leeres Slice, wenn die Syntax einen Slice erzeugen könnte, der nicht vorhanden ist.

Betrachten Sie das folgende Beispiel:

```fsharp
let l = [ 1..10 ]
let a = [| 1..10 |]
let s = "hello!"

let emptyList = l.[-2..(-1)]
let emptyArray = a.[-2..(-1)]
let emptyString = s.[-2..(-1)]
```

> [!IMPORTANT]
> C#-Entwickler erwarten möglicherweise, dass diese eine Ausnahme auslösen, anstatt einen leeren Slice zu liefern. Dies ist eine Entwurfs Entscheidung, die auf die Tatsache beruht, dass leere Auflistungen in F # verfasst werden. Eine leere f #-Liste kann mit einer anderen f #-Liste zusammengesetzt werden, eine leere Zeichenfolge kann einer vorhandenen Zeichenfolge hinzugefügt werden usw. Es kann üblich sein, Slices auf der Grundlage von Werten zu verwenden, die als Parameter weitergegeben werden, und die Toleranz außerhalb der Grenzen > durch die Erstellung einer leeren Auflistung, die mit der kompositorischen Natur von F #-Code zu erreichen ist.

## <a name="fixed-index-slices-for-3d-and-4d-arrays"></a>Blöcke mit fester Indexgröße für 3D-und 4D-Arrays

Bei F #-3D-und 4D-Arrays können Sie einen bestimmten Index "korrigieren" und andere Dimensionen mit fester Größe in einem Slice teilen.

Um dies zu veranschaulichen, sehen Sie sich das folgende 3D-Array an:

*z = 0*

| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 0 | 1 |
| **1** | 2 | 3 |

*z = 1*

| x\y   | 0 | 1 |
|-------|---|---|
| **0** | 4 | 5 |
| **1** | 6 | 7 |

Wenn Sie den Slice `[| 4; 5 |]` aus dem Array extrahieren möchten, verwenden Sie einen Slice mit fester Indexgröße.

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

Die letzte Zeile korrigiert die `y` `z` Indizes und des 3D-Arrays und übernimmt die restlichen `x` Werte, die der Matrix entsprechen.

## <a name="see-also"></a>Weitere Informationen

- [Indizierte Eigenschaften](./members/indexed-properties.md)
