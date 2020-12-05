---
title: Was ist F#?
description: 'Informieren Sie sich über die Programmiersprache f # und die f #-Programmierung. Hier finden Sie Informationen zu umfangreichen Datentypen, Funktionen und deren Anpassung.'
ms.date: 08/03/2018
ms.openlocfilehash: a6bad3e1db63c3fe948b5916925d5eb24a18a41c
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739476"
---
# <a name="what-is-f"></a><span data-ttu-id="32fe0-104">Was ist F?\#</span><span class="sxs-lookup"><span data-stu-id="32fe0-104">What is F\#</span></span>

<span data-ttu-id="32fe0-105">F # ist eine funktionale Programmiersprache, die das Schreiben von korrekter und verwalbbarem Code erleichtert.</span><span class="sxs-lookup"><span data-stu-id="32fe0-105">F# is a functional programming language that makes it easy to write correct and maintainable code.</span></span>

<span data-ttu-id="32fe0-106">F #-Programmierung umfasst hauptsächlich das Definieren von Typen und Funktionen, die vom Typ abgeleitet und automatisch generalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="32fe0-106">F# programming primarily involves defining types and functions that are type-inferred and generalized automatically.</span></span> <span data-ttu-id="32fe0-107">Dies ermöglicht es Ihnen, sich auf die Problemdomäne zu konzentrieren und die Daten zu bearbeiten, statt die Programmier Details zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="32fe0-107">This allows your focus to remain on the problem domain and manipulating its data, rather than the details of programming.</span></span>

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
    |> List.iter (fun greeting -> printfn $"{greeting}")

    0
```

<span data-ttu-id="32fe0-108">F # verfügt über zahlreiche Features, darunter:</span><span class="sxs-lookup"><span data-stu-id="32fe0-108">F# has numerous features, including:</span></span>

* <span data-ttu-id="32fe0-109">Lightweight-Syntax</span><span class="sxs-lookup"><span data-stu-id="32fe0-109">Lightweight syntax</span></span>
* <span data-ttu-id="32fe0-110">Standardmäßig unveränderlich</span><span class="sxs-lookup"><span data-stu-id="32fe0-110">Immutable by default</span></span>
* <span data-ttu-id="32fe0-111">Typrückschluss und automatische Generalisierung</span><span class="sxs-lookup"><span data-stu-id="32fe0-111">Type inference and automatic generalization</span></span>
* <span data-ttu-id="32fe0-112">Funktionen erster Klasse</span><span class="sxs-lookup"><span data-stu-id="32fe0-112">First-class functions</span></span>
* <span data-ttu-id="32fe0-113">Leistungsstarke Datentypen</span><span class="sxs-lookup"><span data-stu-id="32fe0-113">Powerful data types</span></span>
* <span data-ttu-id="32fe0-114">Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="32fe0-114">Pattern matching</span></span>
* <span data-ttu-id="32fe0-115">Asynchrone Programmierung</span><span class="sxs-lookup"><span data-stu-id="32fe0-115">Async programming</span></span>

<span data-ttu-id="32fe0-116">Ein vollständiger Satz von Funktionen wird in der [F #-Sprachreferenz](./language-reference/index.md)dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="32fe0-116">A full set of features are documented in the [F# language reference](./language-reference/index.md).</span></span>

## <a name="rich-data-types"></a><span data-ttu-id="32fe0-117">Rich-Datentypen</span><span class="sxs-lookup"><span data-stu-id="32fe0-117">Rich data types</span></span>

<span data-ttu-id="32fe0-118">Mit Datentypen wie [Datensätzen](./language-reference/records.md) und Unterscheidungs- [Unions](./language-reference/discriminated-unions.md) können Sie komplexe Daten und Domänen darstellen.</span><span class="sxs-lookup"><span data-stu-id="32fe0-118">Data types such as [Records](./language-reference/records.md) and [Discriminated Unions](./language-reference/discriminated-unions.md) let you represent complex data and domains.</span></span>

```fsharp
// Group data with Records
type SuccessfulWithdrawal =
    { Amount: decimal
      Balance: decimal }

type FailedWithdrawal =
    { Amount: decimal
      Balance: decimal
      IsOverdraft: bool }

// Use discriminated unions to represent data of 1 or more forms
type WithdrawalResult =
    | Success of SuccessfulWithdrawal
    | InsufficientFunds of FailedWithdrawal
    | CardExpired of System.DateTime
    | UndisclosedFailure
```

<span data-ttu-id="32fe0-119">F #-Datensätze und Unterscheidungs-Unions sind nicht NULL, unveränderlich und standardmäßig vergleichbar, sodass Sie sehr einfach zu verwenden sind.</span><span class="sxs-lookup"><span data-stu-id="32fe0-119">F# records and discriminated unions are non-null, immutable, and comparable by default, making them very easy to use.</span></span>

## <a name="enforced-correctness-with-functions-and-pattern-matching"></a><span data-ttu-id="32fe0-120">Erzwingen der Richtigkeit mit Funktionen und Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="32fe0-120">Enforced correctness with functions and pattern matching</span></span>

<span data-ttu-id="32fe0-121">F #-Funktionen sind in der Praxis leicht zu deklarieren und leistungsfähig.</span><span class="sxs-lookup"><span data-stu-id="32fe0-121">F# functions are easy to declare and powerful in practice.</span></span> <span data-ttu-id="32fe0-122">Wenn Sie mit [Muster](./language-reference/pattern-matching.md)Abgleich kombiniert werden, können Sie das Verhalten definieren, dessen Richtigkeit durch den Compiler erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="32fe0-122">When combined with [pattern matching](./language-reference/pattern-matching.md), they allow you to define behavior whose correctness is enforced by the compiler.</span></span>

```fsharp
// Returns a WithdrawalResult
let withdrawMoney amount = // Implementation elided

let handleWithdrawal amount =
    let w = withdrawMoney amount

    // The F# compiler enforces accounting for each case!
    match w with
    | Success s -> printfn "Successfully withdrew %f{s.Amount}"
    | InsufficientFunds f -> printfn "Failed: balance is %f{f.Balance}"
    | CardExpired d -> printfn "Failed: card expired on {d}"
    | UndisclosedFailure -> printfn "Failed: unknown :("
```

<span data-ttu-id="32fe0-123">F #-Funktionen sind ebenfalls die erste Klasse, was bedeutet, dass Sie als Parameter und von anderen Funktionen zurückgegeben werden können.</span><span class="sxs-lookup"><span data-stu-id="32fe0-123">F# functions are also first-class, meaning they can be passed as parameters and returned from other functions.</span></span>

## <a name="functions-to-define-operations-on-objects"></a><span data-ttu-id="32fe0-124">Funktionen zum Definieren von Vorgängen für Objekte</span><span class="sxs-lookup"><span data-stu-id="32fe0-124">Functions to define operations on objects</span></span>

<span data-ttu-id="32fe0-125">F # bietet vollständige Unterstützung für-Objekte, bei denen es sich um nützliche Datentypen handelt, wenn Sie Daten und Funktionen mischen müssen.</span><span class="sxs-lookup"><span data-stu-id="32fe0-125">F# has full support for objects, which are useful data types when you need to blend data and functionality.</span></span> <span data-ttu-id="32fe0-126">F #-Funktionen werden verwendet, um-Objekte zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="32fe0-126">F# functions are used to manipulate objects.</span></span>

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

<span data-ttu-id="32fe0-127">Anstatt Code zu schreiben, der objektorientiert ist, schreiben Sie in F # häufig Code, der Objekte als einen anderen Datentyp für die Bearbeitung von Funktionen behandelt.</span><span class="sxs-lookup"><span data-stu-id="32fe0-127">Rather than writing code that is object-oriented, in F#, you will often write code that treats objects as another data type for functions to manipulate.</span></span> <span data-ttu-id="32fe0-128">Funktionen wie [generische Schnittstellen](./language-reference/interfaces.md), [Objekt Ausdrücke](./language-reference/object-expressions.md)und eine kluge [Verwendung von](./language-reference/members/index.md) Membern sind in größeren F #-Programmen üblich.</span><span class="sxs-lookup"><span data-stu-id="32fe0-128">Features such as [generic interfaces](./language-reference/interfaces.md), [object expressions](./language-reference/object-expressions.md), and judicious use of [members](./language-reference/members/index.md) are common in larger F# programs.</span></span>

## <a name="next-steps"></a><span data-ttu-id="32fe0-129">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="32fe0-129">Next steps</span></span>

<span data-ttu-id="32fe0-130">Weitere Informationen zu einem größeren Satz von f #-Features finden Sie in der [f #-Tour](tour.md).</span><span class="sxs-lookup"><span data-stu-id="32fe0-130">To learn more about a larger set of F# features, check out the [F# Tour](tour.md).</span></span>
