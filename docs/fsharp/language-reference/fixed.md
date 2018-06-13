---
title: Fixed-Schlüsselwort (f#)
description: Erfahren Sie, wie "angeheftet werden können" wird eine lokale im Stapel, um zu verhindern, dass die Auflistung mit den f# "-Schlüsselwort fest".
ms.date: 04/24/2017
ms.openlocfilehash: 913ee4d7b0f6b2437793d4788e53556d6be6c4db
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33563875"
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="5695f-103">Fixed-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="5695f-103">The Fixed Keyword</span></span>

<span data-ttu-id="5695f-104">F#-4.1 führt die `fixed` Schlüsselwort, das Ihnen ermöglicht, eine lokale im Stapel, um zu verhindern, dass sie erfasst oder während der Garbage Collection verschoben "anheften".</span><span class="sxs-lookup"><span data-stu-id="5695f-104">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="5695f-105">Sie wird für die Low-Level Programmierszenarien verwendet.</span><span class="sxs-lookup"><span data-stu-id="5695f-105">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="5695f-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="5695f-106">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="5695f-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5695f-107">Remarks</span></span>

<span data-ttu-id="5695f-108">Dies erweitert die Syntax von Ausdrücken, um einen Zeiger zu extrahieren und binden Sie ihn in einen Namen verhindert gesammelt oder während der Garbage Collection verschoben wird, zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="5695f-108">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="5695f-109">Ist ein Zeiger von einem Ausdruck fest, über die `fixed` Schlüsselwort gebunden ist, um einen Bezeichner über die `use` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="5695f-109">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="5695f-110">Die Semantik dieser ähneln ressourcenverwaltung über die `use` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="5695f-110">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="5695f-111">Der Zeiger wird festgelegt, während er befindet sich im Bereich, und sobald sie außerhalb des gültigen Bereichs ist, ist es nicht mehr fest.</span><span class="sxs-lookup"><span data-stu-id="5695f-111">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="5695f-112">`fixed` kann nicht verwendet werden, außerhalb des Kontexts einer `use` Bindung.</span><span class="sxs-lookup"><span data-stu-id="5695f-112">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="5695f-113">Sie müssen den Zeiger in einen Namen mit binden `use`.</span><span class="sxs-lookup"><span data-stu-id="5695f-113">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="5695f-114">Verwenden von `fixed` muss innerhalb eines Ausdrucks in einer Funktion oder eine Methode erfolgen.</span><span class="sxs-lookup"><span data-stu-id="5695f-114">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="5695f-115">Es kann nicht in einem Bereich Skriptebene oder Modulebene verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5695f-115">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="5695f-116">Wie alle Zeiger Code Dies ist eine unsichere Funktion und wird bei Verwendung eine Warnung ausgeben.</span><span class="sxs-lookup"><span data-stu-id="5695f-116">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="5695f-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5695f-117">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="5695f-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5695f-118">See Also</span></span>

[<span data-ttu-id="5695f-119">NativePtr-Modul</span><span class="sxs-lookup"><span data-stu-id="5695f-119">NativePtr Module</span></span>](https://msdn.microsoft.com/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
