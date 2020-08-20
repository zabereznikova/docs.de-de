---
title: Ergebnisse
description: 'Erfahren Sie, wie Sie den F #-Typ "result" verwenden, um fehlertoleranten Code zu schreiben.'
ms.date: 08/13/2020
ms.openlocfilehash: d69e6ddc37bcf5cb5fc28644d59a11a822b83faa
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656917"
---
# <a name="results"></a><span data-ttu-id="0dcbc-103">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="0dcbc-103">Results</span></span>

<span data-ttu-id="0dcbc-104">Der- `Result<'T,'TFailure>` Typ ermöglicht es Ihnen, fehlertoleranten Code zu schreiben, der zusammengesetzt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0dcbc-104">The `Result<'T,'TFailure>` type lets you write error-tolerant code that can be composed.</span></span>

## <a name="syntax"></a><span data-ttu-id="0dcbc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="0dcbc-105">Syntax</span></span>

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a><span data-ttu-id="0dcbc-106">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="0dcbc-106">Remarks</span></span>

<span data-ttu-id="0dcbc-107">Weitere Informationen finden Sie unter dem- [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) Modul für die integrierten Kombinatoren für `Result` .</span><span class="sxs-lookup"><span data-stu-id="0dcbc-107">See the [`Result`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-resultmodule.html) module for the built-in combinators for the `Result`.</span></span> <span data-ttu-id="0dcbc-108">umgewandelt.</span><span class="sxs-lookup"><span data-stu-id="0dcbc-108">type.</span></span>

<span data-ttu-id="0dcbc-109">Beachten Sie, dass der Ergebnistyp eine Struktur Unterscheidungs- [Union](discriminated-unions.md#struct-discriminated-unions)ist.</span><span class="sxs-lookup"><span data-stu-id="0dcbc-109">Note that the result type is a [struct discriminated union](discriminated-unions.md#struct-discriminated-unions).</span></span> <span data-ttu-id="0dcbc-110">Strukturelle Gleichheits Semantik wird hier angewendet.</span><span class="sxs-lookup"><span data-stu-id="0dcbc-110">Structural equality semantics apply here.</span></span>

<span data-ttu-id="0dcbc-111">Der `Result` Typ wird in der Regel in der monadische-Fehlerbehandlung verwendet, die in der F #-Community oft als [Bahn orientierte Programmierung](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="0dcbc-111">The `Result` type is typically used in monadic error-handling, which is often referred to as [Railway-oriented Programming](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) within the F# community.</span></span>  <span data-ttu-id="0dcbc-112">Diese Vorgehensweise wird im folgenden trivialen Beispiel veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="0dcbc-112">The following trivial example demonstrates this approach.</span></span>

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

<span data-ttu-id="0dcbc-113">Wie Sie sehen können, ist es recht einfach, verschiedene Validierungs Funktionen zu verketten, wenn Sie erzwingen, dass Sie eine zurückgeben `Result` .</span><span class="sxs-lookup"><span data-stu-id="0dcbc-113">As you can see, it's quite easy to chain together various validation functions if you force them all to return a `Result`.</span></span>  <span data-ttu-id="0dcbc-114">Auf diese Weise können Sie Funktionen wie diese in kleine Teile aufteilen, die so zusammensetzbar sind, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="0dcbc-114">This lets you break up functionality like this into small pieces which are as composable as you need them to be.</span></span>  <span data-ttu-id="0dcbc-115">Dies hat auch den zusätzlichen Wert, um die Verwendung des [Muster](pattern-matching.md) Abgleich am Ende einer überprüfungsrunde zu *erzwingen* , die wiederum einen höheren Grad an Programm Richtigkeit erzwingt.</span><span class="sxs-lookup"><span data-stu-id="0dcbc-115">This also has the added value of *enforcing* the use of [pattern matching](pattern-matching.md) at the end of a round of validation, which in turns enforces a higher degree of program correctness.</span></span>

## <a name="see-also"></a><span data-ttu-id="0dcbc-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="0dcbc-116">See also</span></span>

- [<span data-ttu-id="0dcbc-117">Unterscheidungs-Unions</span><span class="sxs-lookup"><span data-stu-id="0dcbc-117">Discriminated Unions</span></span>](discriminated-unions.md)
- [<span data-ttu-id="0dcbc-118">Mustervergleich</span><span class="sxs-lookup"><span data-stu-id="0dcbc-118">Pattern Matching</span></span>](pattern-matching.md)
