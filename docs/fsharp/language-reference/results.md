---
title: Ergebnisse (f#)
description: Erfahren Sie, wie den F#-'Result' Typ zu verwenden, um Sie fehlertolerante Code schreiben.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 04/24/2017
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: a15b5cf1-9055-4481-918c-4c8a051b5829
ms.openlocfilehash: e6535b11464f5de0515c05e6678f6328f48a676a
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="results"></a>Ergebnisse

Ab f# 4.1, es ist ein `Result<'T,'TFailure>` Typ, die Sie verwenden können, für das Schreiben von fehlertoleranten standardcodezeile zusammengesetzt werden kann.

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

Beachten Sie, dass der Rückgabetyp einer [Struktur Unterscheidungs-Union](discriminated-unions.md#struct-discriminated-unions), dies ist eine weitere Funktion, die in f# 4.1 eingeführt.  Semantik der strukturellen gleichheitsüberprüfung hier gelten.

Die `Result` Typ werden in der Regel in monadische Fehlerbehandlung, was häufig als bezeichnet wird [gleich objektorientierte Programmierung](https://swlaschin.gitbooks.io/fsharpforfunandprofit/content/posts/recipe-part2.html) in der f#-Community.  Das folgende einfache Beispiel veranschaulicht diesen Ansatz.

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

Wie Sie sehen können, es ist recht einfach, um verschiedene Validierungsfunktionen für die miteinander verketten, wenn Sie sie alle zurückzugebenden Erzwingen einer `Result`.  Damit können aufteilen Funktionalität wie folgt in kleine Teile aufgeteilt sind als zusammensetzbar, wie Sie benötigt werden.  Dies hat auch den Wert Added *erzwingen* die Verwendung von [Mustervergleich](pattern-matching.md) am Ende einer Rundung der Überprüfung, das wiederum ein höheres Maß an Programm Richtigkeit erzwingt.

## <a name="see-also"></a>Siehe auch

[Unterscheidbare Unions](discriminated-unions.md)

[Mustervergleich](pattern-matching.md)
