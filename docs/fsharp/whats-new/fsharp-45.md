---
title: Neuerungen in F- 4.5 - F-Leitfaden
description: Verschaffen Sie sich einen Überblick über die neuen Funktionen, die in F- 4.5 verfügbar sind.
ms.date: 11/27/2019
ms.openlocfilehash: 560e3dd941f79b76d3b864ba0f6560be154ebc1a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186137"
---
# <a name="whats-new-in-f-45"></a>Neuerungen in F- 4.5

F-4.5 fügt der Sprache F- 4.5 mehrere Verbesserungen hinzu. Viele dieser Funktionen wurden addiert, damit Sie effizienten Code in F- schreiben können, während gleichzeitig sichergestellt wird, dass dieser Code sicher ist. Dies bedeutet, dass der Sprache einige Konzepte und eine erhebliche Menge an Compileranalysen hinzugefügt werden müssen, wenn diese Konstrukte verwendet werden.

## <a name="get-started"></a>Erste Schritte

Die F-4.5 ist in allen .NET Core-Verteilungen und Visual Studio-Tools verfügbar. [Beginnen Sie mit f',](../get-started/index.md) um mehr zu erfahren.

## <a name="span-and-byref-like-structs"></a>Span- und byref-ähnliche Konstruktionen

Mit <xref:System.Span%601> dem in .NET Core eingeführten Typ können Sie Puffer im Arbeitsspeicher in einer stark typisierten Weise darstellen, die nun in F- beginnend mit F-4.5 zulässig ist. Das folgende Beispiel zeigt, wie Sie eine <xref:System.Span%601> Funktion wiederverwenden können, die auf einer mit unterschiedlichen Pufferdarstellungen arbeitet:

```fsharp
let safeSum (bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

// managed memory
let arrayMemory = Array.zeroCreate<byte>(100)
let arraySpan = new Span<byte>(arrayMemory)

safeSum(arraySpan) |> printfn "res = %d"

// native memory
let nativeMemory = Marshal.AllocHGlobal(100);
let nativeSpan = new Span<byte>(nativeMemory.ToPointer(), 100)

safeSum(nativeSpan) |> printfn "res = %d"
Marshal.FreeHGlobal(nativeMemory)

// stack memory
let mem = NativePtr.stackalloc<byte>(100)
let mem2 = mem |> NativePtr.toVoidPtr
let stackSpan = Span<byte>(mem2, 100)

safeSum(stackSpan) |> printfn "res = %d"
```

Ein wichtiger Aspekt dabei ist, dass Span und andere [byref-ähnliche Strukturen](../language-reference/structures.md#byreflike-structs) eine sehr starre statische Analyse haben, die vom Compiler durchgeführt wird und deren Verwendung auf eine Weise eingeschränkt wird, die Sie möglicherweise als unerwartet empfinden. Dies ist der grundlegende Kompromiss zwischen Leistung, Ausdruckskraft und Sicherheit, der in F- 4.5 eingeführt wird.

## <a name="revamped-byrefs"></a>Überarbeitete byrefs

Vor f- 4.5 waren [Byrefs](../language-reference/byrefs.md) in F-Code für zahlreiche Anwendungen unsicher und unsolide. Soundness-Probleme rund um Byrefs wurden in F-4.5 behandelt, und die gleiche statische Analyse für Span- und byref-ähnliche Strukturen wurde ebenfalls angewendet.

### <a name="inreft-and-outreft"></a>inref<'T> und outref<'T>

Um den Begriff eines schreibgeschützten, schreibgeschützten und schreibgeschützten Zeigers darzustellen, `inref<'T>`führt `outref<'T>` F-4.5 die Typen ein, die schreibgeschützte bzw. schreibgeschützte Zeiger darstellen. Jeder hat eine andere Semantik. Sie können z. B. nicht in eine `inref<'T>`: schreiben.

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

Standardmäßig leitet der Typrückschluss verwaltete Zeiger `inref<'T>` so ab, dass sie der unveränderlichen Natur des F-Codes entsprechen, es sei denn, etwas wurde bereits als veränderlich deklariert. Um etwas beschreibbar zu machen, müssen Sie `mutable` einen Typ deklarieren, bevor Sie seine Adresse an eine Funktion oder einen Member übergeben, die ihn bearbeitet. Weitere Informationen finden Sie unter [Byrefs](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Readonly-Strukturen

Beginnend mit F- 4.5 können Sie eine <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> Struktur mit:

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Dadurch können Sie ein veränderbares Element in der Struktur nicht deklarieren und Metadaten aussenden, die es F- und C-Dateien ermöglichen, es als schreibgeschützt zu behandeln, wenn es von einer Assembly verbraucht wird. Weitere Informationen finden Sie unter [ReadOnly structs](../language-reference/structures.md#readonly-structs).

## <a name="void-pointers"></a>Leere Zeiger

Der `voidptr` Typ wird zu F-4.5 hinzugefügt, ebenso wie die folgenden Funktionen:

* `NativePtr.ofVoidPtr`, um einen Leerenzeiger in einen systemeigenen Intzeiger umzuwandeln
* `NativePtr.toVoidPtr`, um einen systemeigenen Int-Zeiger in einen leeren Zeiger zu konvertieren

Dies ist hilfreich, wenn Sie mit einer systemeigenen Komponente zusammenarbeiten, die Leerzeiger verwendet.

## <a name="the-match-keyword"></a>dem `match!`-Schlüsselwort

Das `match!` Schlüsselwort verbessert den Musterabgleich, wenn es sich in einem Berechnungsausdruck befindet:

```fsharp
// Code that returns an asynchronous option
let checkBananaAsync (s: string) =
    async {
        if s = "banana" then
            return Some s
        else
            return None
    }

// Now you can use 'match!'
let funcWithString (s: string) =
    async {
        match! checkBananaAsync s with
        | Some bananaString -> printfn "It's banana!"
        | None -> printfn "%s" s
}
```

Auf diese Weise können Sie Code kürzen, der häufig Mischoptionen (oder andere Typen) mit Berechnungsausdrücken wie async umfasst. Weitere Informationen finden Sie unter [Match!](../language-reference/computation-expressions.md#match).

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a>Entspannte Upcasting-Anforderungen in Array-, Listen- und Sequenzausdrücken

Durch das Mischen von Typen, bei denen man von einem anderen innerhalb von Array-, Listen- `:>` und `upcast`Sequenzausdrücken erben kann, müssen Sie traditionell einen beliebigen abgeleiteten Typ auf den übergeordneten Typ mit oder umsetzen. Dies ist nun entspannt, wie folgt gezeigt:

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Einzugsentspannung für Array- und Listenausdrücke

Vor F-4.5 mussten Sie Array- und Listenausdrücke übermäßig einrücken, wenn sie als Argumente an Methodenaufrufe übergeben wurden. Dies ist nicht mehr erforderlich:

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
