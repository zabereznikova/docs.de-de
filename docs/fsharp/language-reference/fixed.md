---
title: Das fixed-Schlüsselwort
description: 'Erfahren Sie, wie Sie eine lokale auf dem Stapel anheften können, um die Auflistung mit dem F #-Schlüsselwort "Fixed" zu verhindern.'
ms.date: 08/15/2020
ms.openlocfilehash: 786ffd706c243fc83f8fb3afc2201d2a34536372
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559179"
---
# <a name="the-fixed-keyword"></a>Das fixed-Schlüsselwort

Mit dem- `fixed` Schlüsselwort können Sie eine lokale auf dem Stapel anheften, um zu verhindern, dass Sie während der Garbage Collection gesammelt oder verschoben wird.  Sie wird für Programmier Szenarios auf niedriger Ebene verwendet.

## <a name="syntax"></a>Syntax

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Bemerkungen

Dadurch wird die Syntax von Ausdrücken erweitert, sodass ein Zeiger extrahiert und an einen Namen gebunden werden kann, der während der Garbage Collection nicht gesammelt oder verschoben werden kann.  

Ein Zeiger von einem Ausdruck wird durch das `fixed` Schlüsselwort korrigiert, das über das-Schlüsselwort an einen Bezeichner gebunden ist `use` .  Die Semantik dieser ähnelt der Ressourcenverwaltung über das- `use` Schlüsselwort.  Der Zeiger wird korrigiert, während er sich im Gültigkeitsbereich befindet, und sobald er sich außerhalb des gültigen Bereichs befindet, wird er nicht mehr korrigiert.  `fixed` kann nicht außerhalb des Kontexts einer Bindung verwendet werden `use` .  Der Zeiger muss mit an einen Namen gebunden werden `use` .

Die Verwendung von `fixed` muss innerhalb eines Ausdrucks in einer Funktion oder Methode auftreten.  Sie kann nicht auf Skript-oder Modulebene verwendet werden.

Wie beim gesamten Zeiger Code ist dies ein unsicherer Feature, das eine Warnung ausgibt, wenn es verwendet wird.

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

## <a name="see-also"></a>Weitere Informationen

- [NativePtr-Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-nativeinterop-nativeptrmodule.html)
