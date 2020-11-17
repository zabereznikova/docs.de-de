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
# <a name="nameof"></a>Nameof

Der `nameof` Ausdruck erzeugt eine Zeichen folgen Konstante, die mit dem Namen in der Quelle für fast alle F #-Konstrukte in der Quelle übereinstimmt.

## <a name="syntax"></a>Syntax

```fsharp
nameof symbol
nameof<'TGeneric>
```

## <a name="remarks"></a>Hinweise

`nameof` durch Auflösen des an ihn über gebenden Symbols und Generieren des Namens dieses Symbols, wie er im Quellcode deklariert ist. Dies ist in verschiedenen Szenarien hilfreich, z. b. bei der Protokollierung und schützt Ihre Protokollierung vor Änderungen im Quellcode.

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

In der letzten Zeile wird eine Ausnahme ausgelöst, die `"month"` in der Fehlermeldung angezeigt wird.

Sie können einen Namen für fast alle F #-Konstrukte verwenden:

```fsharp
module M =
    let f x = nameof x

printfn $"{(M.f 12)]}"
printfn $"{(nameof M)}"
printfn $"{(nameof M.f)}"
```

`nameof` ist keine erstklassige Funktion und kann nicht als solche verwendet werden. Dies bedeutet, dass Sie nicht partiell angewendet werden kann und dass die Werte nicht über F #-Pipeline Operatoren hinein geleitet werden können.

## <a name="nameof-on-operators"></a>Nameof für Operatoren

Operatoren in F # können auf zwei Arten verwendet werden, als Operator Text selbst oder als Symbol, das das kompilierte Formular darstellt. `nameof` bei einem Operator erzeugt den Namen des Operators, wie er in der Quelle deklariert wird. Um den kompilierten Namen zu erhalten, verwenden Sie den kompilierten Namen in der Quelle:

```fsharp
nameof(+) // "+"
nameof op_Addition // "op_Addition"
```

## <a name="nameof-on-generics"></a>Nameof für Generika

Sie können auch einen Namen für einen generischen Typparameter verwenden, die Syntax unterscheidet sich jedoch:

```fsharp
let f<'a> () = nameof<'a>
f() // "a"
```

`nameof<'TGeneric>` nimmt den Namen des Symbols gemäß der Definition in der Quelle an, nicht den Namen des Typs, der an einer CallSite ersetzt wird.

Der Grund, warum sich die Syntax unterscheidet, ist das Ausrichten an anderen systeminternen F #-Operatoren wie `typeof<>` und `typedefof<>` . Dadurch ist F # konsistent in Bezug auf Operatoren, die auf generische Typen und alles andere in der Quelle reagieren.

## <a name="nameof-in-pattern-matching"></a>Nameof in Musterabgleich

Mit dem [ `nameof` Muster](pattern-matching.md#nameof-pattern) können Sie `nameof` in einem Muster Vergleichs Ausdruck wie folgt verwenden:

```fsharp
let f (str: string) =
    match str with
    | nameof str -> "It's 'str'!"
    | _ -> "It is not 'str'!"

f "str" // matches
f "asdf" // does not match
```
