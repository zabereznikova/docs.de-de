---
title: Ergebnisse
description: Erfahren Sie, wie Sie F# den Ergebnistyp verwenden, um fehlertoleranten Code zu schreiben.
ms.date: 04/24/2017
ms.openlocfilehash: 187aa26ccbaac7e0ec998756377bb7b0489eb1ab
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424849"
---
# <a name="results"></a>Ergebnisse

Ab F# 4,1 gibt es einen `Result<'T,'TFailure>` Typ, den Sie zum Schreiben von fehlertoleranter Code verwenden können, der zusammengesetzt werden kann.

## <a name="syntax"></a>Syntax

```fsharp
// The definition of Result in FSharp.Core
[<StructuralEquality; StructuralComparison>]
[<CompiledName("FSharpResult`2")>]
[<Struct>]
type Result<'T,'TError> =
    | Ok of ResultValue:'T
    | Error of ErrorValue:'TError
```

## <a name="remarks"></a>Hinweise

Beachten Sie, dass der Ergebnistyp eine von der Struktur Unterscheidungs- [Union](discriminated-unions.md#struct-discriminated-unions)ist F# , die eine andere in 4,1 eingeführte Funktion ist.  Strukturelle Gleichheits Semantik wird hier angewendet.

Der `Result` Typ wird in der Regel in der monadische-Fehlerbehandlung verwendet, die in der F# Community häufig als [Bahn orientierte Programmierung](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) bezeichnet wird.  Diese Vorgehensweise wird im folgenden trivialen Beispiel veranschaulicht.

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

Wie Sie sehen können, ist es recht einfach, verschiedene Validierungs Funktionen zu verketten, wenn Sie erzwingen, dass Sie eine `Result`zurückgeben.  Auf diese Weise können Sie Funktionen wie diese in kleine Teile aufteilen, die so zusammensetzbar sind, wie Sie es benötigen.  Dies hat auch den zusätzlichen Wert, um die Verwendung des [Muster](pattern-matching.md) Abgleich am Ende einer überprüfungsrunde zu *erzwingen* , die wiederum einen höheren Grad an Programm Richtigkeit erzwingt.

## <a name="see-also"></a>Siehe auch

- [Unterscheidbare Unions](discriminated-unions.md)
- [Mustervergleich](pattern-matching.md)
