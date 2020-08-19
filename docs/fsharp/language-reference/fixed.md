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
# <a name="the-fixed-keyword"></a><span data-ttu-id="8e8d7-103">Das fixed-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="8e8d7-103">The fixed keyword</span></span>

<span data-ttu-id="8e8d7-104">Mit dem- `fixed` Schlüsselwort können Sie eine lokale auf dem Stapel anheften, um zu verhindern, dass Sie während der Garbage Collection gesammelt oder verschoben wird.</span><span class="sxs-lookup"><span data-stu-id="8e8d7-104">The `fixed` keyword allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="8e8d7-105">Sie wird für Programmier Szenarios auf niedriger Ebene verwendet.</span><span class="sxs-lookup"><span data-stu-id="8e8d7-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="8e8d7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="8e8d7-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="8e8d7-107">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="8e8d7-107">Remarks</span></span>

<span data-ttu-id="8e8d7-108">Dadurch wird die Syntax von Ausdrücken erweitert, sodass ein Zeiger extrahiert und an einen Namen gebunden werden kann, der während der Garbage Collection nicht gesammelt oder verschoben werden kann.</span><span class="sxs-lookup"><span data-stu-id="8e8d7-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="8e8d7-109">Ein Zeiger von einem Ausdruck wird durch das `fixed` Schlüsselwort korrigiert, das über das-Schlüsselwort an einen Bezeichner gebunden ist `use` .</span><span class="sxs-lookup"><span data-stu-id="8e8d7-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="8e8d7-110">Die Semantik dieser ähnelt der Ressourcenverwaltung über das- `use` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="8e8d7-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="8e8d7-111">Der Zeiger wird korrigiert, während er sich im Gültigkeitsbereich befindet, und sobald er sich außerhalb des gültigen Bereichs befindet, wird er nicht mehr korrigiert.</span><span class="sxs-lookup"><span data-stu-id="8e8d7-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="8e8d7-112">`fixed` kann nicht außerhalb des Kontexts einer Bindung verwendet werden `use` .</span><span class="sxs-lookup"><span data-stu-id="8e8d7-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="8e8d7-113">Der Zeiger muss mit an einen Namen gebunden werden `use` .</span><span class="sxs-lookup"><span data-stu-id="8e8d7-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="8e8d7-114">Die Verwendung von `fixed` muss innerhalb eines Ausdrucks in einer Funktion oder Methode auftreten.</span><span class="sxs-lookup"><span data-stu-id="8e8d7-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="8e8d7-115">Sie kann nicht auf Skript-oder Modulebene verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8e8d7-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="8e8d7-116">Wie beim gesamten Zeiger Code ist dies ein unsicherer Feature, das eine Warnung ausgibt, wenn es verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8e8d7-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="8e8d7-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e8d7-117">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="8e8d7-118">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="8e8d7-118">See also</span></span>

- [<span data-ttu-id="8e8d7-119">NativePtr-Modul</span><span class="sxs-lookup"><span data-stu-id="8e8d7-119">NativePtr Module</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-nativeinterop-nativeptrmodule.html)
