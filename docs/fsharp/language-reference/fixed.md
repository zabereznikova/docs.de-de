---
title: Fixed-Schlüsselwort (f#)
description: Erfahren Sie, wie "angeheftet werden können" wird eine lokale im Stapel, um zu verhindern, dass die Auflistung mit den f# "-Schlüsselwort fest".
ms.date: 04/24/2017
ms.openlocfilehash: 913ee4d7b0f6b2437793d4788e53556d6be6c4db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="the-fixed-keyword"></a>Fixed-Schlüsselwort

F#-4.1 führt die `fixed` Schlüsselwort, das Ihnen ermöglicht, eine lokale im Stapel, um zu verhindern, dass sie erfasst oder während der Garbage Collection verschoben "anheften".  Sie wird für die Low-Level Programmierszenarien verwendet.

## <a name="syntax"></a>Syntax

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Hinweise

Dies erweitert die Syntax von Ausdrücken, um einen Zeiger zu extrahieren und binden Sie ihn in einen Namen verhindert gesammelt oder während der Garbage Collection verschoben wird, zu ermöglichen.  

Ist ein Zeiger von einem Ausdruck fest, über die `fixed` Schlüsselwort gebunden ist, um einen Bezeichner über die `use` Schlüsselwort.  Die Semantik dieser ähneln ressourcenverwaltung über die `use` Schlüsselwort.  Der Zeiger wird festgelegt, während er befindet sich im Bereich, und sobald sie außerhalb des gültigen Bereichs ist, ist es nicht mehr fest.  `fixed` kann nicht verwendet werden, außerhalb des Kontexts einer `use` Bindung.  Sie müssen den Zeiger in einen Namen mit binden `use`.

Verwenden von `fixed` muss innerhalb eines Ausdrucks in einer Funktion oder eine Methode erfolgen.  Es kann nicht in einem Bereich Skriptebene oder Modulebene verwendet werden.

Wie alle Zeiger Code Dies ist eine unsichere Funktion und wird bei Verwendung eine Warnung ausgeben.

## <a name="example"></a>Beispiel

```fsharp
open Microsoft.FSharp.NativeInterop

type Point = { mutable X: int; mutable Y: int}

let squareWithPointer (p: nativeptr<int>) =
    // Dereference the pointer at the 0th address.
    let mutable value = NativePtr.get p 0

    // Perform some work
    value <- value * value

    // Set the value in the pointer at the 0th address.
    NativePtr.set p 0 value

let pnt = { X = 1; Y = 2 }
printfn "pnt before - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 2

// Note that the use of 'fixed' is inside a function.
// You cannot fix a pointer at a script-level or module-level scope.
let doPointerWork() =
    use ptr = fixed &pnt.Y

    // Square the Y value
    squareWithPointer ptr
    printfn "pnt after - X: %d Y: %d" pnt.X pnt.Y // prints 1 and 4

doPointerWork()
```

## <a name="see-also"></a>Siehe auch

[NativePtr-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
