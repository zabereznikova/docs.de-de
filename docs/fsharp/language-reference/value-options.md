---
title: Wertoptionen
description: Erfahren Sie mehr über die F# Option "Value"-Typ, der ist eine Version der Struktur des Typs Option.
ms.date: 02/06/2019
ms.openlocfilehash: e1036c83189c853b3704d94ca245e4818acc98c1
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828032"
---
# <a name="value-options"></a>Wertoptionen

Die Option "Value"-Typ in F# wird verwendet, wenn halten die folgenden Fällen:

1. Ein Szenario eignet sich für ein [F#-Option](options.md).
2. Verwenden eine Struktur bietet einen Leistungsvorteil in Ihrem Szenario.

Nicht alle Szenarien die Leistung "gelöst" werden Strukturen. Berücksichtigen Sie die zusätzliche Kosten der kopieren, wenn sie anstelle von Verweistypen mit ein. Allerdings große F# Programme instanziieren häufig viele optionale Typen, die langsamsten Pfade durchlaufen und Strukturen können in diesen Fällen ergeben häufig eine bessere gesamtleistung während der Lebensdauer eines Programms.

## <a name="definition"></a>Definition

Option "Value" ist definiert als eine [diskriminierte Union](discriminated-unions.md#struct-discriminated-unions) ähnelt der Option-Verweistyp. Auf diese Weise kann ihre Definition betrachtet werden:

```fsharp
[<StructuralEquality; StructuralComparison>]
[<Struct>]
type ValueOption<'T> =
    | ValueNone
    | ValueSome of 'T
```

Option "Value" entspricht strukturelle Gleichheit und Vergleich. Der Hauptunterschied besteht darin, dass der kompilierte Name, Typnamen und Groß-/Kleinschreibung Namen anzugeben, dass es sich um einen Werttyp handelt.

## <a name="using-value-options"></a>Mithilfe der Wertoptionen

Wertoptionen wie dienen [Optionen](options.md). `ValueSome` wird verwendet, um anzugeben, dass ein Wert vorhanden ist und `ValueNone` wird verwendet, wenn ein Wert nicht vorhanden ist:

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

Wie bei [Optionen](options.md), die Namenskonvention für eine Funktion, die gibt `ValueOption` besteht darin, ihn mit Präfix `try`.

## <a name="value-option-properties-and-methods"></a>Werteigenschaften und Methoden

Es gibt eine Eigenschaft für die Werte können zu diesem Zeitpunkt: `Value`. Ein <xref:System.InvalidOperationException> wird ausgelöst, wenn kein Wert vorhanden ist, wenn diese Eigenschaft aufgerufen wird.

## <a name="value-option-functions"></a>Wert der Option-Funktionen

Es gibt derzeit eine Modul-Bound-Funktion für Wertoptionen, `defaultValueArg`:

```fsharp
val defaultValueArg : arg:'T voption -> defaultValue:'T -> 'T 
```

Wie bei der `defaultArg` Funktion `defaultValueArg` zugrunde liegenden Wert der angegebenen Option "Value" zurückgegeben, falls es vorhanden ist; andernfalls wird den angegebene Standardwert zurückgegeben.

Zu diesem Zeitpunkt müssen Sie keine anderen Modul-Bound-Funktionen für Wertoptionen vorhanden sind.

## <a name="see-also"></a>Siehe auch

- [Optionen](options.md)
