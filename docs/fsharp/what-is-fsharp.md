---
title: Was ist f#
description: Erfahren Sie, was der F#-Programmiersprache und f#-Programmierung wie. Informationen Sie zu Datentypen, Funktionen und deren Zusammenwirken.
ms.date: 08/03/2018
ms.openlocfilehash: 193747f380c61a387ed79ecca6abbcd90ee74376
ms.sourcegitcommit: db8b83057d052c1f9f249d128b08d4423af0f7c2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/02/2018
ms.locfileid: "43863295"
---
# <a name="what-is-f"></a>Was ist f# #

F# ist eine funktionale Programmiersprache, die es einfach macht, die richtigen und verwaltbaren Code zu schreiben.

F#-Programmierung wird in erster Linie an, Definieren von Typen und Funktionen, die automatisch generalisiert und Typ abgeleitet. Dadurch können sich der Fokus auf der Problemdomäne und bearbeiten die Details der Programmierung, anstatt die Daten verbleiben.

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

F# verfügt über zahlreiche Features, darunter:

* Einfache syntax
* Standardmäßig unveränderlich
* Typrückschluss und automatische Verallgemeinerung
* Funktionen
* Leistungsstarke-Datentypen
* Musterabgleich
* Asynchrone Programmierung

Ein vollständiger Satz von Features sind in dokumentiert die [F#-Sprachreferenz](language-reference/index.md).

## <a name="rich-data-types"></a>Rich-Datentypen

Datentypen wie [Datensätze](language-reference/records.md) und [Unterscheidungs-Unions](language-reference/discriminated-unions.md) können Sie komplexe Daten und Domänen darstellen.

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

F#-Datensätze und Unterscheidungs-Unions sind ungleich Null, unveränderliche und vergleichbare standardmäßig, sodass sie sehr einfach zu verwenden.

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a>Erzwungene Richtigkeit mit Funktionen und des musterabgleichs

F#-Funktionen sind einfach zu deklarieren und leistungsstarke in der Praxis. In Kombination mit [Musterabgleich](language-reference/pattern-matching.md), können Sie sich zur Verhalten definieren, deren Richtigkeit wird vom Compiler erzwungen.

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

F#-Funktionen sind auch erstklassige, d. h., sie als Parameter übergeben und von anderen Funktionen zurückgegeben werden können.

## <a name="functions-to-define-operations-on-objects"></a>Funktionen, um Vorgänge für Objekte zu definieren.

F# bietet vollständige Unterstützung für Objekte, die nützliche Daten-Typen sind, wenn Sie Daten und Funktionen in blend müssen. F#-Funktionen werden verwendet, um Objekte zu bearbeiten.

```fsharp
type Set<[<EqualityConditionOn>] ‘T when ‘T: comparison>(elements: seq<'T>) =
    member s.IsEmpty = // Implementation elided
    member s.Contains (value) =// Implementation elided
    member s.Add (value) = // Implementation elided
    // ...
    // Further Implementation elided
    // ...
    interface IEnumerable<‘T>
    interface IReadOnlyCollection<‘T>

[<RequireQualifiedAccess>]
module Set =
    let isEmpty (set: Set<'T>) = set.IsEmpty

    let contains element (set: Set<'T>) = set.Contains(element)

    let add value (set: Set<'T>) = set.Add(value)
```

Anstatt das Schreiben von Code, der objektorientiert, in f# ist, Schreiben häufig Sie Code, die behandelt werden, wie ein anderer Datentyp für die Funktionen zum Bearbeiten. Funktionen, z. B. [generische Schnittstellen](language-reference/interfaces.md), [Objektausdrücke](language-reference/object-expressions.md), und zielgerichtete Verwendung von [Mitglieder](language-reference/members/index.md) werden häufig in größeren F#-Programmen.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu einen größeren Satz von F#-Funktionen, sehen Sie sich die [F#-Tour](tour.md).