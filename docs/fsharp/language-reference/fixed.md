---
title: Das Fixed-Schlüsselwort (f#)
description: Erfahren Sie, wie Sie "anheften" wird eine lokale im Stapel, um zu verhindern, dass bei der Sammlung mit den F#-'Schlüsselwort fixed".
ms.date: 04/24/2017
ms.openlocfilehash: 1bf1b2ad67d2dd7f854e569cfca7c06e8aec7f4c
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43779229"
---
# <a name="the-fixed-keyword"></a>Das Fixed-Schlüsselwort

F# 4.1 führt die `fixed` -Schlüsselwort, das Ihnen ermöglicht, eine lokale im Stapel, um zu verhindern, dass es gesammelt oder während der Garbage Collection verschoben "anheften".  Sie wird für Low-Level Programmierszenarios verwendet.

## <a name="syntax"></a>Syntax

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a>Hinweise

Dadurch wird die Syntax von Ausdrücken können Sie einen Zeiger zu extrahieren und binden Sie ihn in einen Namen verhindert gesammelt oder während der Garbage Collection verschoben wird, erweitert.  

Ein Zeiger von einem Ausdruck wurde behoben, über die `fixed` Schlüsselwort gebunden ist, auf einen Bezeichner über die `use` Schlüsselwort.  Die Semantik dieser ähneln denen auf die ressourcenverwaltung, über die `use` Schlüsselwort.  Der Zeiger wurde behoben, während er im Gültigkeitsbereich befindet, und sobald sie außerhalb des gültigen Bereichs ist, ist es nicht mehr festgelegt.  `fixed` kann nicht verwendet werden, außerhalb des Kontexts einer `use` Bindung.  Sie müssen den Zeiger in einen Namen mit binden `use`.

Verwenden von `fixed` muss innerhalb eines Ausdrucks zu einer Funktion oder Methode erfolgen.  Es kann nicht in einem Skript auf Serverebene oder auf Modulebene Bereich verwendet werden.

Wie alle Zeiger-Code Dies ist eine unsichere-Funktion und gibt eine Warnung generiert wird.

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

- [NativePtr-Modul](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
