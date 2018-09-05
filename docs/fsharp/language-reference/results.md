---
title: Ergebnisse (f#)
description: Erfahren Sie, wie den F#-'Result' Typ zu verwenden, um Sie fehlertoleranten Code schreiben.
ms.date: 04/24/2017
ms.openlocfilehash: a7ce2e1f6b8c6a32d99a2feaf9547c4b67b152b8
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/05/2018
ms.locfileid: "43749248"
---
# <a name="results"></a><span data-ttu-id="fd608-103">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="fd608-103">Results</span></span>

<span data-ttu-id="fd608-104">Ab f# 4.1, es ist ein `Result<'T,'TFailure>` geben, die Sie verwenden können, für das Schreiben von fehlertoleranten Code, der zusammengesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fd608-104">Starting with F# 4.1, there is a `Result<'T,'TFailure>` type which you can use for writing error-tolerant code which can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="fd608-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="fd608-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="fd608-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fd608-106">Remarks</span></span>

<span data-ttu-id="fd608-107">Beachten Sie, dass der Rückgabetyp einer [diskriminierte Union](discriminated-unions.md#struct-discriminated-unions), dies ist ein weiteres Feature, die in f# 4.1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="fd608-107">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions), which is another feature introduced in F# 4.1.</span></span>  <span data-ttu-id="fd608-108">Strukturelle Gleichheitssemantik gelten hier.</span><span class="sxs-lookup"><span data-stu-id="fd608-108">Structural equality semantics apply here.</span></span>

<span data-ttu-id="fd608-109">Die `Result` Typ wird normalerweise verwendet, bei der monadische-Fehlerbehandlung, die häufig als bezeichnet wird [Eisenbahn objektorientierte Programmierung](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) in der F#-Community.</span><span class="sxs-lookup"><span data-stu-id="fd608-109">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="fd608-110">Das folgende einfache Beispiel veranschaulicht diesen Ansatz.</span><span class="sxs-lookup"><span data-stu-id="fd608-110">The following trivial example demonstrates this approach.</span></span>

```fsharp
// Define a simple type which has fields that can be validated
type Request = 
    { Name: string
      Email: string }

// Define some logic for what defines a valid name.
//
// Generates a Result which is an Ok if the name validates;
// otherwise, it generates a Result which is an Error.
let validateName req =
    match req.Name with
    | null -> Error "No name found."
    | "" -> Error "Name is empty."
    | "bananas" -> Error "Bananas is not a name."
    | _ -> Ok req

// Similarly, define some email validation logic.
let validateEmail req =
    match req.Email with
    | null -> Error "No email found."
    | "" -> Error "Email is empty."
    | s when s.EndsWith("bananas.com") -> Error "No email from bananas.com is allowed."
    | _ -> Ok req

let validateRequest reqResult =
    reqResult 
    |> Result.bind validateName
    |> Result.bind validateEmail

let test() = 
    // Now, create a Request and pattern match on the result.
    let req1 = { Name = "Phillip"; Email = "phillip@contoso.biz" }
    let res1 = validateRequest (Ok req1)
    match res1 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "My request was valid!  Name: Phillip Email: phillip@consoto.biz"

    let req2 = { Name = "Phillip"; Email = "phillip@bananas.com" }
    let res2 = validateRequest (Ok req2)
    match res2 with
    | Ok req -> printfn "My request was valid! Name: %s Email %s" req.Name req.Email
    | Error e -> printfn "Error: %s" e
    // Prints: "Error: No email from bananas.com is allowed."

test()
```

<span data-ttu-id="fd608-111">Wie Sie sehen können, ist es recht einfach, verschiedene Validierungsfunktionen miteinander zu verketten, wenn Sie sie alle zurückgeben Erzwingen einer `Result`.</span><span class="sxs-lookup"><span data-stu-id="fd608-111">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="fd608-112">So können Sie Funktionen wie folgt in kleine Teile aufteilen sind als zusammensetzbar, wie Sie diese benötigen.</span><span class="sxs-lookup"><span data-stu-id="fd608-112">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="fd608-113">Dies hat auch dem Mehrwert des *erzwingen* die Verwendung von [Musterabgleich](pattern-matching.md) am Ende einer Rundung der Überprüfung, das wiederum ein höheres Maß an Richtigkeit des Programms erzwingt.</span><span class="sxs-lookup"><span data-stu-id="fd608-113">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="fd608-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fd608-114">See also</span></span>

- [<span data-ttu-id="fd608-115">Unterscheidbare Unions</span><span class="sxs-lookup"><span data-stu-id="fd608-115">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="fd608-116">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="fd608-116">Pattern Matching</span></span>](pattern-matching.md)
