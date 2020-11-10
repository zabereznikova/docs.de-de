---
title: Was ist F#?
description: 'Informieren Sie sich über die Programmiersprache f # und die f #-Programmierung. Hier finden Sie Informationen zu umfangreichen Datentypen, Funktionen und deren Anpassung.'
ms.date: 08/03/2018
ms.openlocfilehash: 37dc2f472d65a046e4bf67e672e2a96f4d4afded
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/10/2020
ms.locfileid: "94439651"
---
# <a name="what-is-f"></a>Was ist F?\#

F # ist eine funktionale Programmiersprache, die das Schreiben von korrekter und verwalbbarem Code erleichtert.

F #-Programmierung umfasst hauptsächlich das Definieren von Typen und Funktionen, die vom Typ abgeleitet und automatisch generalisiert werden. Dies ermöglicht es Ihnen, sich auf die Problemdomäne zu konzentrieren und die Daten zu bearbeiten, statt die Programmier Details zu bearbeiten.

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name = $"Hello, {name}! Isn't F# great?"

[<EntryPoint>]
let main args =
    // Defines a list of names
    let names = [ "Don"; "Julia"; "Xi" ]

    // Prints a greeting for each name!
    names
    |> List.map getGreeting
    |> List.iter (fun greeting -> printfn "%s" greeting)

    0
```

F # verfügt über zahlreiche Features, darunter:

* Lightweight-Syntax
* Standardmäßig unveränderlich
* Typrückschluss und automatische Generalisierung
* Funktionen erster Klasse
* Leistungsstarke Datentypen
* Musterabgleich
* Asynchrone Programmierung

Ein vollständiger Satz von Funktionen wird in der [F #-Sprachreferenz](./language-reference/index.md)dokumentiert.

## <a name="rich-data-types"></a>Rich-Datentypen

Mit Datentypen wie [Datensätzen](./language-reference/records.md) und Unterscheidungs- [Unions](./language-reference/discriminated-unions.md) können Sie komplexe Daten und Domänen darstellen.

```fsharp
// Group data with Records
type SuccessfulWithdrawal = {
    Amount: decimal
    Balance: decimal
}

type FailedWithdrawal = {
    Amount: decimal
    Balance: decimal
    IsOverdraft: bool
}

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

F #-Datensätze und Unterscheidungs-Unions sind nicht NULL, unveränderlich und standardmäßig vergleichbar, sodass Sie sehr einfach zu verwenden sind.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Erzwingen der Richtigkeit mit Funktionen und Musterabgleich

F #-Funktionen sind in der Praxis leicht zu deklarieren und leistungsfähig. Wenn Sie mit [Muster](./language-reference/pattern-matching.md)Abgleich kombiniert werden, können Sie das Verhalten definieren, dessen Richtigkeit durch den Compiler erzwungen wird.

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f" s.Amount
    | InsufficientFunds f -> printfn "Failed: balance is %f" f.Balance
    | CardExpired d -> printfn "Failed: card expired on %O" d
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

F #-Funktionen sind ebenfalls die erste Klasse, was bedeutet, dass Sie als Parameter und von anderen Funktionen zurückgegeben werden können.

## <a name="functions-to-define-operations-on-objects"></a>Funktionen zum Definieren von Vorgängen für Objekte

F # bietet vollständige Unterstützung für-Objekte, bei denen es sich um nützliche Datentypen handelt, wenn Sie Daten und Funktionen mischen müssen. F #-Funktionen werden verwendet, um-Objekte zu bearbeiten.

```fsharp
type Set<'T when 'T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

Anstatt Code zu schreiben, der objektorientiert ist, schreiben Sie in F # häufig Code, der Objekte als einen anderen Datentyp für die Bearbeitung von Funktionen behandelt. Funktionen wie [generische Schnittstellen](./language-reference/interfaces.md), [Objekt Ausdrücke](./language-reference/object-expressions.md)und eine kluge [Verwendung von](./language-reference/members/index.md) Membern sind in größeren F #-Programmen üblich.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu einem größeren Satz von f #-Features finden Sie in der [f #-Tour](tour.md).
