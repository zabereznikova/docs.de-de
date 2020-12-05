---
title: Byrefs
description: 'Erfahren Sie mehr über ByRef-und ByRef-ähnliche Typen in F #, die für die Low-Level-Programmierung verwendet werden.'
ms.date: 11/04/2019
ms.openlocfilehash: ff2c06d8940f7341d5d8b1d942be264bfac586c5
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2020
ms.locfileid: "96740314"
---
# <a name="byrefs"></a>Byrefs

F # verfügt über zwei wichtige Featurebereiche, die sich auf den Raum von Low-Level-Programmierung befassen:

* Die `byref` / `inref` / `outref` Typen, bei denen es sich um verwaltete Zeiger handelt. Sie haben Einschränkungen hinsichtlich der Verwendung, sodass Sie kein Programm kompilieren können, das zur Laufzeit ungültig ist.
* Eine `byref` -like- [Struktur](structures.md) , bei der es sich um eine-Struktur mit ähnlicher Semantik und denselben Einschränkungen der Kompilierzeit wie handelt `byref<'T>` . Ein Beispiel hierfür ist <xref:System.Span%601> .

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

Es gibt drei Formen von `byref` :

* `inref<'T>`, ein verwalteter Zeiger zum Lesen des zugrunde liegenden Werts.
* `outref<'T>`, ein verwalteter Zeiger zum Schreiben in den zugrunde liegenden Wert.
* `byref<'T>`, ein verwalteter Zeiger zum Lesen und Schreiben des zugrunde liegenden Werts.

Ein `byref<'T>` kann übermittelt werden, `inref<'T>` Wenn erwartet wird. Auf ähnliche Weise kann ein-Wert über `byref<'T>` mittelt werden, an dem `outref<'T>` erwartet wird.

## <a name="using-byrefs"></a>Verwenden von ByRefs

Um einen zu verwenden `inref<'T>` , benötigen Sie einen Zeiger Wert mit `&` :

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn $"Now: %O{dt}"

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Um mithilfe von oder in den Zeiger zu `outref<'T>` schreiben `byref<'T>` , müssen Sie auch den Wert, auf den Sie einen Zeiger ziehen, festlegen `mutable` .

```fsharp
open System

let f (dt: byref<DateTime>) =
    printfn $"Now: %O{dt}"
    dt <- DateTime.Now

// Make 'dt' mutable
let mutable dt = DateTime.Now

// Now you can pass the pointer to 'dt'
f &dt
```

Wenn Sie nur den Zeiger schreiben, anstatt ihn zu lesen, sollten Sie `outref<'T>` anstelle von verwenden `byref<'T>` .

### <a name="inref-semantics"></a>Inref-Semantik

Betrachten Sie folgenden Code:

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

Semantisch bedeutet dies Folgendes:

* Der Inhaber des `x` Zeigers darf ihn nur zum Lesen des Werts verwenden.
* Jeder Zeiger, der für die in geschachtelten `struct` Felder abgerufen `SomeStruct` wird, erhält den Typ `inref<_>` .

Außerdem gilt Folgendes:

* Es gibt keine Auswirkung darauf, dass andere Threads oder Aliase keinen Schreibzugriff auf haben `x` .
* Es gibt keine Implikation, die `SomeStruct` aufgrund der Verwendung eines unveränderlich ist `x` `inref` .

Bei F #-Werttypen, die unveränderlich **sind** , wird der Zeiger jedoch als `this` abgeleitet `inref` .

Alle diese Regeln bedeuten, dass der Inhaber eines `inref` Zeigers den unmittelbaren Inhalt des Speichers, auf den verwiesen wird, möglicherweise nicht ändert.

### <a name="outref-semantics"></a>Leistungs Semantik

Der Zweck von `outref<'T>` ist, anzugeben, dass der Zeiger nur in geschrieben werden soll. Unerwartet `outref<'T>` ermöglicht das Lesen des zugrunde liegenden Werts trotz des Namens. Dies dient zu Kompatibilitätszwecken. Semantisch `outref<'T>` ist nicht anders als `byref<'T>` .

### <a name="interop-with-c"></a>Interop mit C\#

C# unterstützt `in ref` die `out ref` Schlüsselwörter und zusätzlich zu den `ref` Rückgabe von. In der folgenden Tabelle wird gezeigt, wie F # interpretiert, was c# ausgibt:

|C#-Konstrukt|F #-Infer|
|------------|---------|
|`ref` Rückgabewert|`outref<'T>`|
|`ref readonly` Rückgabewert|`inref<'T>`|
|`in ref`-Parameter|`inref<'T>`|
|`out ref`-Parameter|`outref<'T>`|

In der folgenden Tabelle wird gezeigt, was F # ausgibt:

|F #-Konstrukt|Ausgegebenes Konstrukt|
|------------|-----------------|
|`inref<'T>`-Argument|`[In]` Attribut für Argument|
|`inref<'T>` hre|`modreq` Attribut für Wert|
|`inref<'T>` im abstrakten Slot oder in der Implementierung|`modreq` on-Argument oder Return|
|`outref<'T>`-Argument|`[Out]` Attribut für Argument|

### <a name="type-inference-and-overloading-rules"></a>Typrückschluss und Überladen von Regeln

Ein- `inref<'T>` Typ wird durch den F #-Compiler in den folgenden Fällen abgeleitet:

1. Ein .net-Parameter oder-Rückgabetyp mit einem- `IsReadOnly` Attribut.
2. Der `this` Zeiger auf einen Strukturtyp ohne änderbare Felder.
3. Die Adresse eines Speicher Orts, der von einem anderen Zeiger abgeleitet ist `inref<_>` .

Wenn eine implizite Adresse eines verwendet wird `inref` , wird eine Überladung mit einem Argument vom Typ einer `SomeType` Überladung mit einem Argument vom Typ bevorzugt `inref<SomeType>` . Zum Beispiel:

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

In beiden Fällen werden die Überladungen, die nehmen, `System.DateTime` aufgelöst und nicht die über Ladungen, die von übernommen werden `inref<System.DateTime>` .

## <a name="byref-like-structs"></a>ByRef-ähnliche Strukturen

Zusätzlich zum `byref` / `inref` / `outref` Trio können Sie auch eigene Strukturen definieren, die der `byref` ähnlichen Semantik entsprechen können. Dies erfolgt mit dem- <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> Attribut:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` impliziert nicht `Struct` . Beides muss für den Typ vorhanden sein.

Eine " `byref` -like"-Struktur in F # ist ein Stapel gebundener Werttyp. Sie wird niemals dem verwalteten Heap zugeordnet. Eine `byref` ähnliche Struktur eignet sich für Hochleistungs Programmierung, da Sie mit einer Reihe von starken Überprüfungen zur Lebensdauer und nicht Erfassung erzwungen wird. Die Regeln lauten wie folgt:

* Sie können als Funktionsparameter, Methoden Parameter, lokale Variablen und Methoden Rückgaben verwendet werden.
* Sie können keine statischen Member oder Instanzmember einer Klasse oder einer normalen Struktur sein.
* Sie können nicht von einem Closure-Konstrukt ( `async` Methoden oder Lambda-Ausdrücke) aufgezeichnet werden.
* Sie können nicht als generischer Parameter verwendet werden.

Dieser letzte Punkt ist entscheidend für die Programmierung im F #-Pipeline Stil, ebenso wie `|>` eine generische Funktion, die die Eingabetypen parametrisiert. Diese Einschränkung kann für `|>` in Zukunft gelockert werden, da Sie Inline ist und keine Aufrufe von nicht Inline-generischen Funktionen im Textkörper vornimmt.

Wenngleich diese Regeln die Nutzung stark einschränken, wird dies durchgeführt, um die Zusage von Hochleistungs Computing auf sichere Weise zu erfüllen.

## <a name="byref-returns"></a>ByRef-Rückgaben

ByRef-Rückgabe von F #-Funktionen oder-Membern können erstellt und genutzt werden. Wenn eine `byref` -Rückgabe Methode genutzt wird, wird der Wert implizit dereferenziert. Zum Beispiel:

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn $"%d{squared}"
```

Um einen ByRef-Wert zurückzugeben, muss die Variable, die den Wert enthält, länger als der aktuelle Bereich sein.
Verwenden Sie außerdem `&value` (wobei value eine Variable ist, die länger als der aktuelle Bereich ist), um ByRef zurückzugeben.

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

Verwenden Sie `&x` (wobei `x` der Wert ist), um die implizite Dereferenzierung zu vermeiden, z. b. das Übergeben eines Verweises über mehrere verkettete Aufrufe.

Sie können auch eine Rückgabe direkt zuweisen `byref` . Sehen Sie sich das folgende (hochgradig imperative) Programm an:

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
    printfn $"Original sequence: %O{c}"

    let v = &c.FindLargestSmallerThan 16

    v <- v*2 // Directly assign to the byref return

    printfn $"New sequence:      %O{c}"

    0 // return an integer exit code
```

Dies ist die Ausgabe:

```console
Original sequence: 1 3 7 15 31 63 127 255 511 1023
New sequence:      1 3 7 30 31 63 127 255 511 1023
```

## <a name="scoping-for-byrefs"></a>Bereichs Definition für ByRefs

`let`Der Verweis auf einen gebundenen Wert kann nicht den Bereich überschreiten, in dem er definiert wurde. Beispielsweise ist Folgendes nicht zulässig:

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

Dadurch wird verhindert, dass Sie unterschiedliche Ergebnisse erhalten, je nachdem, ob Sie mit Optimierungen kompilieren oder nicht.
