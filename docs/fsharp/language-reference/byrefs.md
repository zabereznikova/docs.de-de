---
title: Byrefs
description: Erfahren Sie mehr über byref- und byref-ähnliche Typen in F', die für die Low-Level-Programmierung verwendet werden.
ms.date: 11/04/2019
ms.openlocfilehash: 527f465ee87fe153a2deae1306b6730531dc4123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187055"
---
# <a name="byrefs"></a>Byrefs

Die F-Funktion hat zwei Hauptbereiche, die sich im Bereich der Low-Level-Programmierung befassen:

* `byref` / Die `inref` / Typen, bei denen es sich um verwaltete Zeiger `outref` handelt. Sie haben Nutzungseinschränkungen, sodass Sie ein Programm nicht kompilieren können, das zur Laufzeit ungültig ist.
* Eine `byref`-like-Struktur, bei der es sich um eine [Struktur](structures.md) handelt, `byref<'T>`die eine ähnliche Semantik und die gleichen Kompilierungszeiteinschränkungen wie aufweist. Ein Beispiel <xref:System.Span%601>ist .

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

## <a name="byref-inref-and-outref"></a>Byref, inref und outref

Es gibt drei `byref`Formen von:

* `inref<'T>`, ein verwalteter Zeiger zum Lesen des zugrunde liegenden Werts.
* `outref<'T>`, ein verwalteter Zeiger zum Schreiben in den zugrunde liegenden Wert.
* `byref<'T>`, ein verwalteter Zeiger zum Lesen und Schreiben des zugrunde liegenden Werts.

A `byref<'T>` kann dort `inref<'T>` übergeben werden, wo ein erwartet wird. Ebenso kann `byref<'T>` ein übergeben `outref<'T>` werden, wo ein erwartet wird.

## <a name="using-byrefs"></a>Verwenden von byrefs

Um eine `inref<'T>`zu verwenden, müssen Sie `&`einen Zeigerwert mit :

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let usage =
    let dt = DateTime.Now
    f &dt // Pass a pointer to 'dt'
```

Um mithilfe eines `outref<'T>` oder `byref<'T>`in den Zeiger zu schreiben, müssen Sie `mutable`auch den Wert erstellen, den Sie an einem Zeiger an.

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

Wenn Sie nur den Zeiger schreiben, anstatt `outref<'T>` ihn `byref<'T>`zu lesen, sollten Sie anstelle von verwenden.

### <a name="inref-semantics"></a>Inref-Semantik

Betrachten Sie folgenden Code:

```fsharp
let f (x: inref<SomeStruct>) = x.SomeField
```

Semantisch bedeutet dies Folgendes:

* Der Halter `x` des Zeigers darf ihn nur zum Lesen des Werts verwenden.
* Jeder Zeiger, `struct` der zu `SomeStruct` Feldern gelangt `inref<_>`ist, die in feldern verschachtelt sind, wird vom Typ angegeben.

Das Folgende gilt auch:

* Es gibt keine Implikation, dass andere Threads `x`oder Aliase keinen Schreibzugriff auf haben.
* Es gibt keine Implikation, die `SomeStruct` `x` unveränderlich ist, da sie eine `inref`ist.

Für Unveränderliche F-Werttypen wird **are** `this` der Zeiger jedoch als eine `inref`abgeleitet.

Alle diese Regeln zusammen bedeuten, `inref` dass der Inhaber eines Zeigers den unmittelbaren Inhalt des speicherweisen Speichers nicht ändern darf.

### <a name="outref-semantics"></a>Outref-Semantik

Der Zweck `outref<'T>` von ist anzugeben, dass der Zeiger nur geschrieben werden sollte. Unerwartet, `outref<'T>` erlaubt das Lesen des zugrunde liegenden Werts trotz seines Namens. Dies dient zu Kompatibilitätszwecken. Semantisch ist `outref<'T>` nicht anders `byref<'T>`als .

### <a name="interop-with-c"></a>Interop mit C\#

Neben den `in ref` `out ref` `ref` Rückgaben unterstützt C- die und-Schlüsselwörter. In der folgenden Tabelle wird gezeigt, wie die Von-Mail-Datei interpretiert wird, was die Emittungen von C-Code ausstrahlen:

|C-Konstrukt|F-Abfolge|
|------------|---------|
|`ref`Rückgabewert|`outref<'T>`|
|`ref readonly`Rückgabewert|`inref<'T>`|
|`in ref`-Parameter|`inref<'T>`|
|`out ref`-Parameter|`outref<'T>`|

Die folgende Tabelle zeigt, was die E-Mail-Sendungen von F- aussenden:

|F-Konstrukt|Emitiertes Konstrukt|
|------------|-----------------|
|`inref<'T>`-Argument|`[In]`Attribut auf Argument|
|`inref<'T>`Rückgabe|`modreq`Attribut auf Wert|
|`inref<'T>`in abstraktem Steckplatz oder Implementierung|`modreq`auf Argument oder Rückgabe|
|`outref<'T>`-Argument|`[Out]`Attribut auf Argument|

### <a name="type-inference-and-overloading-rules"></a>Typrückschluss- und Überladungsregeln

In `inref<'T>` den folgenden Fällen wird ein Typ vom F-Compiler abgeleitet:

1. Ein .NET-Parameter oder Rückgabetyp mit einem `IsReadOnly` Attribut.
2. Der `this` Zeiger auf einen Strukturtyp, der keine veränderlichen Felder enthält.
3. Die Adresse eines Speicherspeicherorts, der von einem anderen `inref<_>` Zeiger abgeleitet wurde.

Wenn eine implizite `inref` Adresse von einem übernommen wird, `SomeType` wird eine Überladung mit einem `inref<SomeType>`Argument vom Typ einer Überladung mit einem Argument vom Typ vorgezogen. Beispiel:

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

In beiden Fällen `System.DateTime` werden die Überladungen gelöst `inref<System.DateTime>`und nicht die Überlastungen, die .

## <a name="byref-like-structs"></a>Byref-ähnliche Konstruktionen

`byref` / `inref` / `outref` Zusätzlich zum Trio können Sie eigene Strukturen definieren, `byref`die sich an -like semantics halten können. Dies geschieht <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> mit dem Attribut:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike`bedeutet `Struct`nicht . Beide müssen auf dem Typ vorhanden sein.

Eine`byref`" -like"-Struktur in F ist ein stapelgebundener Werttyp. Sie wird nie auf dem verwalteten Heap zugewiesen. Eine `byref`-like struct ist nützlich für die Hochleistungsprogrammierung, da sie mit einer Reihe starker Überprüfungen der Lebensdauer und Nicht-Capture erzwungen wird. Die Regeln sind:

* Sie können als Funktionsparameter, Methodenparameter, lokale Variablen, Methodenrückgaben verwendet werden.
* Sie können keine statischen oder Instanzmember einer Klasse oder normalen Struktur sein.
* Sie können nicht von einem`async` Abschlusskonstrukt erfasst werden (Methoden oder Lambda-Ausdrücke).
* Sie können nicht als generischer Parameter verwendet werden.

Dieser letzte Punkt ist für die Programmierung `|>` im Pipeline-Stil von entscheidender Bedeutung, ebenso wie eine generische Funktion, die ihre Eingabetypen parametrisiert. Diese Einschränkung kann `|>` in Zukunft gelockert werden, da sie inline ist und keine Aufrufe von nicht inline generischen Funktionen in ihrem Körper auslöst.

Obwohl diese Regeln die Nutzung stark einschränken, tun sie dies, um das Versprechen von Hochleistungs-Computing auf sichere Weise zu erfüllen.

## <a name="byref-returns"></a>Byref kehrt zurück

Byref-Rückgaben von F-Funktionen oder -Membern können erzeugt und verbraucht werden. Bei der `byref`Verwendung einer -returning-Methode wird der Wert implizit dereferenziert. Beispiel:

```fsharp
let squareAndPrint (data : byref<int>) =
    let squared = data*data    // data is implicitly dereferenced
    printfn "%d" squared
```

Um einen Wert byref zurückzugeben, muss die Variable, die den Wert enthält, länger als der aktuelle Bereich leben.
Um byref zurückzugeben, `&value` verwenden Sie (wobei wert eine Variable ist, die länger als der aktuelle Bereich lebt).

```fsharp
let mutable sum = 0
let safeSum (bytes: Span<byte>) =
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    &sum  // sum lives longer than the scope of this function.
```

Um die implizite Dereferenzierung zu vermeiden, z. `&x` B. `x` das Übergeben eines Verweises durch mehrere verkettete Aufrufe, verwenden Sie (wobei der Wert ist).

Sie können eine Rücksendung `byref`auch direkt zuweisen. Betrachten Sie das folgende (höchst zwingende) Programm:

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

## <a name="scoping-for-byrefs"></a>Scoping für byrefs

Ein `let`-bound-Wert darf seinen Verweis nicht über den Bereich hinausgehen, in dem er definiert wurde. Beispielsweise ist Folgendes nicht zulässig:

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

Dies verhindert, dass Sie unterschiedliche Ergebnisse erhalten, je nachdem, ob Sie mit Optimierungen kompilieren oder nicht.
