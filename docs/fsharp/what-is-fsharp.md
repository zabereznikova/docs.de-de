---
title: Was ist F#?
description: Erfahren Sie, was die F#-Programmiersprache ausmacht und wie in F# programmiert wird. Hier finden Sie Informationen zu umfangreichen Datentypen, Funktionen und deren Anpassung.
ms.date: 08/03/2018
ms.openlocfilehash: 3cba509f59a8e81e1a0264de7451e9d80304d768
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332731"
---
# <a name="what-is-f"></a>Was ist F\#

F# ist eine funktionale Programmiersprache, die das Schreiben von korrektem und verwaltbarem Code erleichtert.

Die F#-Programmierung umfasst hauptsächlich das Definieren von Typen und Funktionen, die vom Typ abgeleitet und automatisch generalisiert werden. Dies ermöglicht es Ihnen, sich auf die Problemdomäne zu konzentrieren und die Daten zu bearbeiten, statt um die Details der Programmierung.

```fsharp
open System // Gets access to functionality in System namespace.

// Defines a function that takes a name and produces a greeting.
let getGreeting name =
    sprintf "Hello, %s! Isn't F# great?" name

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

F# verfügt über zahlreiche Features, einschließlich:

* Lightweight-Syntax
* Standardmäßig Unveränderliche
* Typrückschluss und automatische Generalisierung
* Funktionen erster Klasse
* Leistungsstarke Datentypen
* Musterabgleich
* Asynchrone Programmierung

Ein vollständiger Satz von Funktionen ist in der [ F# Sprachreferenz](./language-reference/index.md) dokumentiert.

## <a name="rich-data-types"></a>Rich-Datentypen

Mit Datentypen wie [Datensätzen](./language-reference/records.md) und Unterscheidungs-[Unions](./language-reference/discriminated-unions.md) können Sie komplexe Daten und Domänen darstellen.

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

F#-Datensätze und Unterscheidungs-Unions sind nicht NULL, unveränderlich und standardmäßig vergleichbar, sodass Sie sehr einfach zu verwenden sind.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Erzwingen der Richtigkeit mit Funktionen und Musterabgleich

F#-Funktionen sind in der Praxis leicht zu deklarieren und leistungsfähig. Wenn Sie mit [Muster](./language-reference/pattern-matching.md)-Abgleich kombiniert werden, können Sie das Verhalten definieren, dessen Richtigkeit durch den Compiler erzwungen wird.

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

F#-Funktionen sind ebenfalls Funktionen erster Klasse, d. h., Sie können als Parameter und von anderen Funktionen zurückgegeben werden.

## <a name="functions-to-define-operations-on-objects"></a>Funktionen zum Definieren von Vorgängen für Objekte

F# bietet vollständige Unterstützung für Objekte. Dies ist nützlich, wenn Sie Daten und Funktionen mischen müssen. F#-Funktionen werden verwendet, um Objekte zu bearbeiten.

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

Anstatt das Schreiben von Code, der objektorientiert, in F# ist, Schreiben häufig Sie Code, die behandelt werden, wie ein anderer Datentyp für die Funktionen zum Bearbeiten. Funktionen wie [generische Schnittstellen](./language-reference/interfaces.md), [Objektausdrücke](./language-reference/object-expressions.md) und eine kluge [Verwendung von](./language-reference/members/index.md) Membern werden häufig in größeren F#-Programmen verwendet.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu einer größeren Anzahl von F#-Features finden Sie in der [ F# Tour](tour.md).
