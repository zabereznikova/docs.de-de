---
title: "Fixed-Schlüsselwort (f#)"
description: "Erfahren Sie, wie \"angeheftet werden können\" wird eine lokale im Stapel, um zu verhindern, dass die Auflistung mit den f# \"-Schlüsselwort fest\"."
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5795ce1f-11bf-4798-9f1f-6e44ffa1477e
ms.openlocfilehash: ac6be2bb9df8da1b6d0a29c2e27f777eade07cb9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="the-fixed-keyword"></a><span data-ttu-id="16e87-104">Fixed-Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="16e87-104">The Fixed Keyword</span></span>

<span data-ttu-id="16e87-105">F#-4.1 führt die `fixed` Schlüsselwort, das Ihnen ermöglicht, eine lokale im Stapel, um zu verhindern, dass sie erfasst oder während der Garbage Collection verschoben "anheften".</span><span class="sxs-lookup"><span data-stu-id="16e87-105">F# 4.1 introduces the `fixed` keyword, which allows you to "pin" a local onto the stack to prevent it from being collected or moved during garbage-collection.</span></span>  <span data-ttu-id="16e87-106">Sie wird für die Low-Level Programmierszenarien verwendet.</span><span class="sxs-lookup"><span data-stu-id="16e87-106">It is used for low-level programming scenarios.</span></span>

## <a name="syntax"></a><span data-ttu-id="16e87-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="16e87-107">Syntax</span></span>

```fsharp
use ptr = fixed expression
```

## <a name="remarks"></a><span data-ttu-id="16e87-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="16e87-108">Remarks</span></span>

<span data-ttu-id="16e87-109">Dies erweitert die Syntax von Ausdrücken, um einen Zeiger zu extrahieren und binden Sie ihn in einen Namen verhindert gesammelt oder während der Garbage Collection verschoben wird, zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="16e87-109">This extends the syntax of expressions to allow extracting a pointer and binding it to a name which is prevented from being collected or moved during garbage-collection.</span></span>  

<span data-ttu-id="16e87-110">Ist ein Zeiger von einem Ausdruck fest, über die `fixed` Schlüsselwort gebunden ist, um einen Bezeichner über die `use` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="16e87-110">A pointer from an expression is fixed via the `fixed` keyword is bound to an identifier via the `use` keyword.</span></span>  <span data-ttu-id="16e87-111">Die Semantik dieser ähneln ressourcenverwaltung über die `use` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="16e87-111">The semantics of this are similar to resource management via the `use` keyword.</span></span>  <span data-ttu-id="16e87-112">Der Zeiger wird festgelegt, während er befindet sich im Bereich, und sobald sie außerhalb des gültigen Bereichs ist, ist es nicht mehr fest.</span><span class="sxs-lookup"><span data-stu-id="16e87-112">The pointer is fixed while it is in scope, and once it is out of scope, it is no longer fixed.</span></span>  <span data-ttu-id="16e87-113">`fixed`kann nicht verwendet werden, außerhalb des Kontexts einer `use` Bindung.</span><span class="sxs-lookup"><span data-stu-id="16e87-113">`fixed` cannot be used outside the context of a `use` binding.</span></span>  <span data-ttu-id="16e87-114">Sie müssen den Zeiger in einen Namen mit binden `use`.</span><span class="sxs-lookup"><span data-stu-id="16e87-114">You must bind the pointer to a name with `use`.</span></span>

<span data-ttu-id="16e87-115">Verwenden von `fixed` muss innerhalb eines Ausdrucks in einer Funktion oder eine Methode erfolgen.</span><span class="sxs-lookup"><span data-stu-id="16e87-115">Use of `fixed` must occur within an expression in a function or a method.</span></span>  <span data-ttu-id="16e87-116">Es kann nicht in einem Bereich Skriptebene oder Modulebene verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="16e87-116">It cannot be used at a script-level or module-level scope.</span></span>

<span data-ttu-id="16e87-117">Wie alle Zeiger Code Dies ist eine unsichere Funktion und wird bei Verwendung eine Warnung ausgeben.</span><span class="sxs-lookup"><span data-stu-id="16e87-117">Like all pointer code, this is an unsafe feature and will emit a warning when used.</span></span>

## <a name="example"></a><span data-ttu-id="16e87-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="16e87-118">Example</span></span>

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

## <a name="see-also"></a><span data-ttu-id="16e87-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16e87-119">See Also</span></span>

[<span data-ttu-id="16e87-120">NativePtr-Modul</span><span class="sxs-lookup"><span data-stu-id="16e87-120">NativePtr Module</span></span>](https://msdn.microsoft.com/en-us/visualfsharpdocs/conceptual/nativeinterop.nativeptr-module-%5Bfsharp%5D)
