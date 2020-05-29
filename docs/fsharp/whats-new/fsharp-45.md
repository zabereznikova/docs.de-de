---
title: 'Neues in f # 4,5-f #-Handbuch'
description: 'Verschaffen Sie sich einen Überblick über die neuen Features, die in F # 4,5 verfügbar sind.'
ms.date: 11/27/2019
ms.openlocfilehash: 2c978c66a4bf231398508cbc1cbb8839228ea8e9
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84202356"
---
# <a name="whats-new-in-f-45"></a>Neues in F # 4,5

F # 4,5 fügt der Sprache f # mehrere Verbesserungen hinzu. Viele dieser Features wurden hinzugefügt, um Ihnen das Schreiben von effizientem Code in F # zu ermöglichen und gleichzeitig sicherzustellen, dass dieser Code sicher ist. Dies bedeutet, dass Sie der Sprache einige Konzepte hinzufügen und bei der Verwendung dieser Konstrukte eine beträchtliche Menge an compileranalysen hinzufügen.

## <a name="get-started"></a>Erste Schritte

F # 4,5 ist in allen .net Core-Distributionen und Visual Studio-Tools verfügbar. [Beginnen Sie mit F #](../get-started/index.md) , um weitere Informationen zu erhalten.

## <a name="span-and-byref-like-structs"></a>Span-und ByRef-ähnliche Strukturen

Der <xref:System.Span%601> in .net Core eingeführte Typ ermöglicht es Ihnen, Puffer im Arbeitsspeicher in einer stark typisierten Weise darzustellen. Dies ist nun in f # ab f # 4,5 zulässig. Im folgenden Beispiel wird gezeigt, wie Sie eine Funktion, die auf einer <xref:System.Span%601> mit unterschiedlichen Puffer Darstellungen ausgeführt wird, wieder verwenden können:

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

Ein wichtiger Aspekt hierbei ist, dass die Spanne und andere [ByRef-ähnliche Strukturen](../language-reference/structures.md#byreflike-structs) über eine sehr strenge statische Analyse verfügen, die vom Compiler durchgeführt wird und deren Verwendung auf eine Art und Weise einschränkt, die Sie möglicherweise unerwartet finden. Dies ist der grundlegende Kompromiss zwischen Leistung, Ausdrucksfähigkeit und Sicherheit, der in F # 4,5 eingeführt wird.

## <a name="revamped-byrefs"></a>Überarbeitete ByRefs

Vor f # 4,5 waren [ByRefs](../language-reference/byrefs.md) in F # unsicher und unvernünftig für zahlreiche Anwendungen. Probleme mit der Leistung von ByRefs wurden in F # 4,5 behoben, und die gleiche statische Analyse für Span-und ByRef-ähnliche Strukturen wurde ebenfalls angewendet.

### <a name="inreft-and-outreft"></a>inref< 't> und nicht< 't>

Um das Konzept eines schreibgeschützten, Lese geschützten und Lese-/Schreib-verwalteten Zeigers darzustellen, führt F # 4,5 die- `inref<'T>` ,-Typen ein, die `outref<'T>` schreibgeschützte bzw. schreibgeschützte Zeiger darstellen. Jede hat eine andere Semantik. Beispielsweise können Sie nicht in einen schreiben `inref<'T>` :

```fsharp
let f (dt: inref<DateTime>) =
    dt <- DateTime.Now // ERROR - cannot write to an inref!
```

Standardmäßig leitet der Typrückschluss verwaltete Zeiger so ab, `inref<'T>` dass Sie mit der unveränderlichen Natur von F #-Code übereinstimmen, es sei denn, etwas wurde bereits als änderbar deklariert. Damit etwas beschreibbar ist, müssen Sie einen Typ deklarieren, `mutable` bevor Sie die Adresse an eine Funktion oder einen Member übergeben, der Sie bearbeitet. Weitere Informationen finden Sie unter [ByRefs](../language-reference/byrefs.md).

## <a name="readonly-structs"></a>Schreibgeschützte Strukturen

Ab F # 4,5 können Sie eine Struktur mit kommentieren <xref:System.Runtime.CompilerServices.IsReadOnlyAttribute> :

```fsharp
[<IsReadOnly; Struct>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

Dies ermöglicht es Ihnen nicht, ein änderbares Element in der Struktur zu deklarieren, und gibt Metadaten aus, die F # und c# als schreibgeschützt behandeln können, wenn Sie von einer Assembly verwendet werden. Weitere Informationen finden Sie unter schreibgeschützte [Strukturen](../language-reference/structures.md#readonly-structs).

## <a name="void-pointers"></a>Void-Zeiger

Der `voidptr` Typ wird F # 4,5 hinzugefügt, wie die folgenden Funktionen:

* `NativePtr.ofVoidPtr`So konvertieren Sie einen void-Zeiger in einen systemeigenen int-Zeiger
* `NativePtr.toVoidPtr`So konvertieren Sie einen nativen int-Zeiger in einen void-Zeiger

Dies ist hilfreich, wenn Sie mit einer systemeigenen Komponente interagieren, von der void-Zeiger verwendet werden.

## <a name="the-match-keyword"></a>dem `match!`-Schlüsselwort

Das- `match!` Schlüsselwort erweitert den Musterabgleich, wenn es innerhalb eines Berechnungs Ausdrucks

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

Dies ermöglicht es Ihnen, Code zu verkürzen, der häufig das Mischen von Optionen (oder anderen Typen) mit Berechnungs Ausdrücken wie "Async" einschließt. Weitere Informationen finden Sie unter [Match!](../language-reference/computation-expressions.md#match).

## <a name="relaxed-upcasting-requirements-in-array-list-and-sequence-expressions"></a>Gelockerte upcastanforderungen in Array-, Listen-und Sequenz Ausdrücken

Das Mischen von Typen, bei denen eine von einer anderen innerhalb von Array-, Listen-und Sequenz Ausdrücken erben kann, erforderte in der Regel, dass Sie einen abgeleiteten Typ in seinen übergeordneten Typ mit oder umgewandelt `:>` `upcast` . Dies wird nun gelockert und wie folgt veranschaulicht:

```fsharp
let x0 : obj list  = [ "a" ] // ok pre-F# 4.5
let x1 : obj list  = [ "a"; "b" ] // ok pre-F# 4.5
let x2 : obj list  = [ yield "a" :> obj ] // ok pre-F# 4.5

let x3 : obj list  = [ yield "a" ] // Now ok for F# 4.5, and can replace x2
```

## <a name="indentation-relaxation-for-array-and-list-expressions"></a>Einzug der Einzügen für Array-und Listen Ausdrücke

Vor F # 4,5 mussten Array-und Listen Ausdrücke übermäßig eingezogen werden, wenn Sie als Argumente an Methodenaufrufe übermittelt wurden. Dies ist nicht mehr erforderlich:

```fsharp
module NoExcessiveIndenting =
    System.Console.WriteLine(format="{0}", arg = [|
        "hello"
    |])
    System.Console.WriteLine([|
        "hello"
    |])
```
