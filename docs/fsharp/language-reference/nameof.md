---
title: Nameof
description: Erfahren Sie mehr über den nameof-Operator, eine metaprogrammierfunktion, die es Ihnen ermöglicht, den Namen eines beliebigen Symbols in Ihrem Quellcode zu entwickeln.
ms.date: 11/12/2020
ms.openlocfilehash: 9947d7172d1b73db5c181297ec8b1131382e1f5e
ms.sourcegitcommit: 34968a61e9bac0f6be23ed6ffb837f52d2390c85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "94688633"
---
# <a name="nameof"></a><span data-ttu-id="41a99-103">Nameof</span><span class="sxs-lookup"><span data-stu-id="41a99-103">Nameof</span></span>

<span data-ttu-id="41a99-104">Der `nameof` Ausdruck erzeugt eine Zeichen folgen Konstante, die mit dem Namen in der Quelle für fast alle F #-Konstrukte in der Quelle übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="41a99-104">The `nameof` expression produces a string constant that matches the name in source for nearly any F# construct in source.</span></span>

## <a name="syntax"></a><span data-ttu-id="41a99-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="41a99-105">Syntax</span></span>

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a><span data-ttu-id="41a99-106">Hinweise</span><span class="sxs-lookup"><span data-stu-id="41a99-106">Remarks</span></span>

<span data-ttu-id="41a99-107">`nameof` durch Auflösen des an ihn über gebenden Symbols und Generieren des Namens dieses Symbols, wie er im Quellcode deklariert ist.</span><span class="sxs-lookup"><span data-stu-id="41a99-107">`nameof` works by resolving the symbol passed to it and produces the name of that symbol as it is declared in your source code.</span></span> <span data-ttu-id="41a99-108">Dies ist in verschiedenen Szenarien hilfreich, z. b. bei der Protokollierung und schützt Ihre Protokollierung vor Änderungen im Quellcode.</span><span class="sxs-lookup"><span data-stu-id="41a99-108">This is useful in various scenarios, such as logging, and protects your logging against changes in source code.</span></span>

```fsharp
let months =
    [
        "January"; "February"; "March"; "April";
        "May"; "June"; "July"; "August"; "September";
        "October"; "November"; "December"
    ]

let lookupMonth month =
    if (month > 12 || month < 1) then
        invalidArg (nameof month) ($"Value passed in was %d{month}.")

    months.[month-1]

printfn "%s" (lookupMonth 12)
printfn "%s" (lookupMonth 1)
printfn "%s" (lookupMonth 13)
```

<span data-ttu-id="41a99-109">In der letzten Zeile wird eine Ausnahme ausgelöst, die `"month"` in der Fehlermeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="41a99-109">The last line will throw an exception and `"month"` will be shown in the error message.</span></span>

<span data-ttu-id="41a99-110">Sie können einen Namen für fast alle F #-Konstrukte verwenden:</span><span class="sxs-lookup"><span data-stu-id="41a99-110">You can take a name of nearly every F# construct:</span></span>

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

<span data-ttu-id="41a99-111">`nameof` ist keine erstklassige Funktion und kann nicht als solche verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="41a99-111">`nameof` is not a first-class function and cannot be used as such.</span></span> <span data-ttu-id="41a99-112">Dies bedeutet, dass Sie nicht partiell angewendet werden kann und dass die Werte nicht über F #-Pipeline Operatoren hinein geleitet werden können.</span><span class="sxs-lookup"><span data-stu-id="41a99-112">That means it cannot be partially applied and values cannot be piped into it via F# pipeline operators.</span></span>

## <a name="nameof-on-operators"></a><span data-ttu-id="41a99-113">Nameof für Operatoren</span><span class="sxs-lookup"><span data-stu-id="41a99-113">Nameof on operators</span></span>

<span data-ttu-id="41a99-114">Operatoren in F # können auf zwei Arten verwendet werden, als Operator Text selbst oder als Symbol, das das kompilierte Formular darstellt.</span><span class="sxs-lookup"><span data-stu-id="41a99-114">Operators in F# can be used in two ways, as an operator text itself, or a symbol representing the compiled form.</span></span> <span data-ttu-id="41a99-115">`nameof` bei einem Operator erzeugt den Namen des Operators, wie er in der Quelle deklariert wird.</span><span class="sxs-lookup"><span data-stu-id="41a99-115">`nameof` on an operator will produce the name of the operator as it is declared in source.</span></span> <span data-ttu-id="41a99-116">Um den kompilierten Namen zu erhalten, verwenden Sie den kompilierten Namen in der Quelle:</span><span class="sxs-lookup"><span data-stu-id="41a99-116">To get the compiled name, use the compiled name in source:</span></span>

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a><span data-ttu-id="41a99-117">Nameof für Generika</span><span class="sxs-lookup"><span data-stu-id="41a99-117">Nameof on generics</span></span>

<span data-ttu-id="41a99-118">Sie können auch einen Namen für einen generischen Typparameter verwenden, die Syntax unterscheidet sich jedoch:</span><span class="sxs-lookup"><span data-stu-id="41a99-118">You can also take a name of a generic type parameter, but the syntax is different:</span></span>

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

<span data-ttu-id="41a99-119">`nameof<'TGeneric>` nimmt den Namen des Symbols gemäß der Definition in der Quelle an, nicht den Namen des Typs, der an einer CallSite ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="41a99-119">`nameof<'TGeneric>` will take the name of the symbol as defined in source, not the name of the type substituted at a call site.</span></span>

<span data-ttu-id="41a99-120">Der Grund, warum sich die Syntax unterscheidet, ist das Ausrichten an anderen systeminternen F #-Operatoren wie `typeof<>` und `typedefof<>` .</span><span class="sxs-lookup"><span data-stu-id="41a99-120">The reason why the syntax is different is to align with other F# intrinsic operators like `typeof<>` and `typedefof<>`.</span></span> <span data-ttu-id="41a99-121">Dadurch ist F # konsistent in Bezug auf Operatoren, die auf generische Typen und alles andere in der Quelle reagieren.</span><span class="sxs-lookup"><span data-stu-id="41a99-121">This makes F# consistent with respect to operators that act on generic types and anything else in source.</span></span>

## <a name="nameof-in-pattern-matching"></a><span data-ttu-id="41a99-122">Nameof in Musterabgleich</span><span class="sxs-lookup"><span data-stu-id="41a99-122">Nameof in pattern matching</span></span>

<span data-ttu-id="41a99-123">Mit dem [ `nameof` Muster](pattern-matching.md#nameof-pattern) können Sie `nameof` in einem Muster Vergleichs Ausdruck wie folgt verwenden:</span><span class="sxs-lookup"><span data-stu-id="41a99-123">The [`nameof` pattern](pattern-matching.md#nameof-pattern) lets you use `nameof` in a pattern match expression like so:</span></span>

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
