---
title: Ergebnisse (f#)
description: Erfahren Sie, wie den F#-'Result' Typ zu verwenden, um Sie fehlertolerante Code schreiben.
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 35fd1d3b1590291e18aa28460cf5939606c21d3a
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="results"></a><span data-ttu-id="e09d6-103">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="e09d6-103">Results</span></span>

<span data-ttu-id="e09d6-104">Ab f# 4.1, es ist ein `Result<'T,'TFailure>` Typ, die Sie verwenden können, für das Schreiben von fehlertoleranten standardcodezeile zusammengesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="e09d6-104">Starting with F# 4.1, there is a `Result<'T,'TFailure>` type which you can use for writing error-tolerant code which can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="e09d6-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e09d6-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> = 
    | Ok of ResultValue:'T 
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="e09d6-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e09d6-106">Remarks</span></span>

<span data-ttu-id="e09d6-107">Beachten Sie, dass der Rückgabetyp einer [Struktur Unterscheidungs-Union](discriminated-unions.md#struct-discriminated-unions), dies ist eine weitere Funktion, die in f# 4.1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="e09d6-107">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions), which is another feature introduced in F# 4.1.</span></span>  <span data-ttu-id="e09d6-108">Semantik der strukturellen gleichheitsüberprüfung hier gelten.</span><span class="sxs-lookup"><span data-stu-id="e09d6-108">Structural equality semantics apply here.</span></span>

<span data-ttu-id="e09d6-109">Die `Result` Typ werden in der Regel in monadische Fehlerbehandlung, was häufig als bezeichnet wird [gleich objektorientierte Programmierung](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) in der f#-Community.</span><span class="sxs-lookup"><span data-stu-id="e09d6-109">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="e09d6-110">Das folgende einfache Beispiel veranschaulicht diesen Ansatz.</span><span class="sxs-lookup"><span data-stu-id="e09d6-110">The following trivial example demonstrates this approach.</span></span>

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

<span data-ttu-id="e09d6-111">Wie Sie sehen können, es ist recht einfach, um verschiedene Validierungsfunktionen für die miteinander verketten, wenn Sie sie alle zurückzugebenden Erzwingen einer `Result`.</span><span class="sxs-lookup"><span data-stu-id="e09d6-111">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="e09d6-112">Damit können aufteilen Funktionalität wie folgt in kleine Teile aufgeteilt sind als zusammensetzbar, wie Sie benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="e09d6-112">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="e09d6-113">Dies hat auch den Wert Added *erzwingen* die Verwendung von [Mustervergleich](pattern-matching.md) am Ende einer Rundung der Überprüfung, das wiederum ein höheres Maß an Programm Richtigkeit erzwingt.</span><span class="sxs-lookup"><span data-stu-id="e09d6-113">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="e09d6-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e09d6-114">See Also</span></span>

[<span data-ttu-id="e09d6-115">Unterscheidbare Unions</span><span class="sxs-lookup"><span data-stu-id="e09d6-115">Discriminated Unions</span></span>](discriminated-unions.md)

[<span data-ttu-id="e09d6-116">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="e09d6-116">Pattern Matching</span></span>](pattern-matching.md)
