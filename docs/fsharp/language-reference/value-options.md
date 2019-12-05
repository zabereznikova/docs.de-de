---
title: Wertoptionen
description: Erfahren Sie mehr F# über den Wert Optionstyp, bei dem es sich um eine Struktur Version des Options Typs handelt.
ms.date: 12/04/2019
ms.openlocfilehash: 0e9882ab4acdf2757705ef6022516d3572d87ef2
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837115"
---
# <a name="value-options"></a>Wertoptionen

Die Option "Value"-Typ in F# wird verwendet, wenn halten die folgenden Fällen:

1. Ein Szenario eignet sich für ein [F#-Option](options.md).
2. Die Verwendung einer Struktur bietet einen Leistungsvorteil in Ihrem Szenario.

Nicht alle Leistungs sensiblen Szenarios werden mithilfe von Strukturen "gelöst". Sie müssen die zusätzlichen Kosten für das Kopieren in Erwägung gezogen, wenn Sie Sie anstelle von Verweis Typen verwenden. Große F# Programme instanziieren jedoch häufig viele optionale Typen, die durch heiße Pfade fließen, und in solchen Fällen können Strukturen im Laufe der Lebensdauer eines Programms häufig eine bessere Gesamtleistung erzielen.

## <a name="definition"></a>Definition

Die Value-Option ist als [Struktur](discriminated-unions.md#struct-discriminated-unions) Unterscheidungs-Union definiert, die dem Verweis Optionstyp ähnelt. Die Definition kann sich wie folgt vorstellen:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

Die Option "Value" entspricht Struktur Gleichheit und Vergleich. Der Hauptunterschied besteht darin, dass der kompilierte Name, der Typname und die Fallnamen alle angeben, dass es sich um einen Werttyp handelt.

## <a name="using-value-options"></a>Verwenden von Wert Optionen

Wert Optionen werden genau wie [Optionen](options.md)verwendet. `ValueSome` wird verwendet, um anzugeben, dass ein Wert vorhanden ist, und `ValueNone` verwendet, wenn kein Wert vorhanden ist:

```fsharp
let tryParseDateTime (s: string) =
    match System.DateTime.TryParse(s) with
    | (true, dt) -> ValueSome dt
    | (false, _) -> ValueNone

let possibleDateString1 = "1990-12-25"
let possibleDateString2 = "This is not a date"

let result1 = tryParseDateTime possibleDateString1
let result2 = tryParseDateTime possibleDateString2

match (result1, result2) with
| ValueSome d1, ValueSome d2 -> printfn "Both are dates!"
| ValueSome d1, ValueNone -> printfn "Only the first is a date!"
| ValueNone, ValueSome d2 -> printfn "Only the second is a date!"
| ValueNone, ValueNone -> printfn "None of them are dates!"
```

Wie bei den [Optionen](options.md)wird die Benennungs Konvention für eine Funktion, die `ValueOption` zurückgibt, dem `try`vorangestellt.

## <a name="value-option-properties-and-methods"></a>Eigenschaften und Methoden für Wert Optionen

Zu diesem Zeitpunkt gibt es eine Eigenschaft für Wert Optionen: `Value`. Wenn diese Eigenschaft aufgerufen wird, wird ein <xref:System.InvalidOperationException> ausgelöst, wenn kein Wert vorhanden ist.

## <a name="value-option-functions"></a>Optionen für Wert Optionen

Das `ValueOption`-Modul in FSharp. Core enthält eine entsprechende Funktionalität für das `Option` Modul. Es gibt einige Unterschiede im Namen, wie z. b. `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T
```

Dies verhält sich wie `defaultArg` im `Option`-Modul, arbeitet jedoch stattdessen mit einer Wert Option.

## <a name="see-also"></a>Siehe auch

- [Optionen](options.md)
