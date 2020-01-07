---
title: Byrefs
description: Informationen Sie zu Byref und Byref-ähnlichen Typen in F#, die für die Low-Level-Programmierung verwendet werden.
ms.date: 11/04/2019
ms.openlocfilehash: a6d3d69c4a163be9ecef7e33c284c4a73e800405
ms.sourcegitcommit: 8c99457955fc31785b36b3330c4ab6ce7984a7ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/29/2019
ms.locfileid: "75545130"
---
# <a name="byrefs"></a>Byrefs

F#verfügt über zwei wichtige Featurebereiche, die sich auf den Raum der Low-Level-Programmierung befassen:

* Die `byref`/`inref`/`outref` Typen, bei denen es sich um verwaltete Zeiger handelt. Sie haben Einschränkungen hinsichtlich der Verwendung, sodass Sie kein Programm kompilieren können, das zur Laufzeit ungültig ist.
* Eine `byref`ähnliche Struktur, bei der es sich um eine [Struktur](structures.md) mit ähnlicher Semantik und denselben Kompilierzeit Beschränkungen wie `byref<'T>`handelt. Ein Beispiel hierfür ist <xref:System.Span%601>.

## <a name="syntax"></a>Syntax

```fsharp
// Byref types as parameters
let f (x: byref<'T>) = ()
let g (x: inref<'T>) = ()
let h (x: outref<'T>) = ()

// Calling a function with a byref parameter
let mutable x = 3
f &x

// Declaring a byref-like struct
open System.Runtime.CompilerServices

[<Struct; IsByRefLike>]
type S(count1: int, count2: int) =
    member x.Count1 = count1
    member x.Count2 = count2
```

## <a name="byref-inref-and-outref"></a>ByRef, inref und der Wert

Es gibt drei Arten von `byref`:

* `inref<'T>`, ein verwalteter Zeiger zum Lesen des zugrunde liegenden Werts.
* `outref<'T>`, ein verwalteter Zeiger zum Schreiben in den zugrunde liegenden Wert.
* `byref<'T>`, ein verwalteter Zeiger zum Lesen und Schreiben des zugrunde liegenden Werts.

Eine `byref<'T>` kann an die Stelle, an der ein `inref<'T>` erwartet wird Auf ähnliche Weise kann eine `byref<'T>` an die Stelle, an der ein `outref<'T>` erwartet wird

## <a name="using-byrefs"></a>Verwenden von ByRefs

Um einen `inref<'T>`zu verwenden, müssen Sie einen Zeiger Wert mit `&`erhalten:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Wenn Sie mit einem `outref<'T>` oder `byref<'T>`in den Zeiger schreiben möchten, müssen Sie auch den Wert, auf den Sie einen Zeiger ziehen, auf `mutable`festlegen.

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn "Now: %s" (dt.ToString())
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

Wenn Sie nur den Zeiger schreiben, anstatt ihn zu lesen, sollten Sie die Verwendung von `outref<'T>` anstelle von `byref<'T>`in Erwägung gezogen.

### <a name="inref-semantics"></a>Inref-Semantik

Betrachten Sie folgenden Code:

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

Semantisch bedeutet dies Folgendes:

* Der Besitzer des `x` Zeigers darf ihn nur zum Lesen des Werts verwenden.
* Jeder Zeiger, der `struct` in `SomeStruct` geschachtelten Feldern abgerufen wird, erhält den Typ `inref<_>`.

Außerdem gilt Folgendes:

* Es gibt keine Auswirkung darauf, dass andere Threads oder Aliase keinen Schreibzugriff auf `x`haben.
* Es gibt keine Auswirkung darauf, dass `SomeStruct` aufgrund `x` einer `inref`unveränderlich ist.

Bei F# Werttypen, die unveränderlich **sind** , wird der `this` Zeiger als `inref`abgeleitet.

Alle diese Regeln bedeuten, dass der Besitzer eines `inref` Zeigers den unmittelbaren Inhalt des Speichers, auf den verwiesen wird, möglicherweise nicht ändert.

### <a name="outref-semantics"></a>Leistungs Semantik

Der Zweck `outref<'T>` ist, anzugeben, dass der Zeiger nur in den Zeiger geschrieben werden soll. Unerwartet, `outref<'T>` das Lesen des zugrunde liegenden Werts trotz seines Namens zulässt. Dies dient zu Kompatibilitätszwecken. `outref<'T>` unterscheidet sich semantisch von `byref<'T>`.

### <a name="interop-with-c"></a>Interop mit C-\#

C#unterstützt die Schlüsselwörter `in ref` und `out ref` zusätzlich zu `ref`-Rückgabe. Die folgende Tabelle zeigt, wie F# interpretiert wie c# ausgibt:

|C#Erstellen|F#leitet|
|------------|---------|
|`ref` Rückgabewert|`outref<'T>`|
|`ref readonly` Rückgabewert|`inref<'T>`|
|`in ref`-Parameter|`inref<'T>`|
|`out ref`-Parameter|`outref<'T>`|

Die folgende Tabelle zeigt, was F# ausgibt:

|F#Erstellen|Ausgegebenes Konstrukt|
|------------|-----------------|
|`inref<'T>`-Argument|`[In]`-Attribut für Argument|
|`inref<'T>` Rückgabe|`modreq` Attribut für Wert|
|`inref<'T>` im abstrakten Slot oder in der Implementierung|`modreq` on-Argument oder Rückgabe|
|`outref<'T>`-Argument|`[Out]`-Attribut für Argument|

### <a name="type-inference-and-overloading-rules"></a>Typrückschluss und Überladen von Regeln

Ein `inref<'T>` Typ wird vom F# Compiler in den folgenden Fällen abgeleitet:

1. Ein .net-Parameter oder-Rückgabetyp, der über ein `IsReadOnly` Attribut verfügt.
2. Der `this` Zeiger auf einen Strukturtyp ohne änderbare Felder.
3. Die Adresse eines Speicher Orts, der von einem anderen `inref<_>` Zeiger abgeleitet ist.

Wenn eine implizite Adresse eines `inref` übernommen wird, wird eine Überladung mit einem Argument vom Typ `SomeType` einer Überladung mit einem Argument vom Typ `inref<SomeType>`bevorzugt. Beispiel:

```fsharp
type C() =
    static member M(x: System.DateTime) = x.AddDays(1.0)
    static member M(x: inref<System.DateTime>) = x.AddDays(2.0)
    static member M2(x: System.DateTime, y: int) = x.AddDays(1.0)
    static member M2(x: inref<System.DateTime>, y: int) = x.AddDays(2.0)

let res = System.DateTime.Now
let v =  C.M(res)
let v2 =  C.M2(res, 4)
```

In beiden Fällen werden die über Ladungen, die `System.DateTime` Unternehmen, aufgelöst, anstatt die über Ladungen `inref<System.DateTime>`.

## <a name="byref-like-structs"></a>ByRef-ähnliche Strukturen

Zusätzlich zum `byref`/`inref`/`outref` Trio können Sie eigene Strukturen definieren, die `byref`ähnlichen Semantik entsprechen können. Dies erfolgt mit dem <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute>-Attribut:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` impliziert keine `Struct`. Beides muss für den Typ vorhanden sein.

Ein "`byref`-wie" "Struct" in F# ist ein Stack gebundene Wert. Sie wird niemals dem verwalteten Heap zugeordnet. Eine `byref`ähnliche Struktur eignet sich für die Hochleistungs Programmierung, da Sie mit einer Reihe von leistungsstarken Überprüfungen zur Lebensdauer und nicht Erfassung erzwungen wird. Dies sind die Regeln:

* Sie können als Funktionsparameter, Methoden Parameter, lokale Variablen und Methoden Rückgaben verwendet werden.
* Sie können keine statischen Member oder Instanzmember einer Klasse oder einer normalen Struktur sein.
* Sie können nicht von einem Closure-Konstrukt (`async`-Methoden oder Lambda-Ausdrücken) aufgezeichnet werden.
* Sie können nicht als generischer Parameter verwendet werden.

Dieser letzte Punkt ist entscheidend für F# die Programmierung im Pipeline Stil, da `|>` eine generische Funktion ist, die seine Eingabetypen parametrisiert. Diese Einschränkung kann für `|>` in der Zukunft gelockert werden, da Sie Inline ist und keine Aufrufe von nicht Inline-generischen Funktionen im Textkörper vornimmt.

Wenngleich diese Regeln die Nutzung stark einschränken, wird dies durchgeführt, um die Zusage von Hochleistungs Computing auf sichere Weise zu erfüllen.

## <a name="byref-returns"></a>ByRef-Rückgaben

ByRef-Rückgaben von F#-Funktionen oder Elemente erstellt und verwendet werden können. Bei der Verwendung einer `byref`zurück gebenden Methode wird der Wert implizit dereferenziert. Beispiel:

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

Um die implizite Dereferenzierung zu vermeiden, z. b. einen Verweis über mehrere verkettete Aufrufe zu übergeben, verwenden Sie `&x` (wobei `x` der Wert ist).

Sie können einem Rückgabe `byref`auch direkt zuweisen. Sehen Sie sich das folgende (hochgradig imperative) Programm an:

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override _.ToString() = String.Join(' ', nums)

    member _.FindLargestSmallerThan(target: int) =
        let mutable ctr = nums.Length - 1

        while ctr > 0 && nums.[ctr] >= target do ctr <- ctr - 1

        if ctr > 0 then &nums.[ctr] else &nums.[0]

[<EntryPoint>]
let main argv =
    let c = C()
    printfn "Original sequence: %s" (c.ToString())

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn "New sequence:      %s" (c.ToString())

    0 // return an integer exit code
```

Dies ist die Ausgabe:

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>Bereichs Definition für ByRefs

Ein `let`gebundener Wert kann nicht den Bereich überschreiten, in dem er definiert wurde. Beispielsweise ist Folgendes nicht zulässig:

```fsharp
let test2 () =
    let x = 12
    &x // Error: 'x' exceeds its defined scope!

let test () =
    let x =
        let y = 1
        &y // Error: `y` exceeds its defined scope!
    ()
```

Dadurch wird verhindert, dass Sie unterschiedliche Ergebnisse erhalten, je nachdem, ob Sie mit Optimierungen ein-oder ausschalten.
