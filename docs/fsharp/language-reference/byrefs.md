---
title: Parametry (f#)
description: Informationen Sie zu Byref und Byref-ähnlichen Typen in f#, die für die Low-Level-Programmierung verwendet werden.
ms.date: 09/02/2018
ms.openlocfilehash: 6131104e4325f77da84368c337f998c6b2b5309b
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45508303"
---
# <a name="byrefs"></a>Parametry

F# verfügt über zwei Hauptfunktionen, die sich im Bereich der Programmierung auf unterer Ebene beschäftigen:

* Die `byref` / `inref` / `outref` Typen, die einen verwalteten Zeiger. Sie haben Einschränkungen bei der Nutzung, sodass Sie ein Programm kompilieren nicht möglich, die zur Laufzeit ungültig ist.
* Ein `byref`– wie Struktur, die ist eine [Struktur](structures.md) hat ähnliche Semantik und die gleichen Einschränkungen während der Kompilierung wie `byref<'T>`. Ein Beispiel ist die <xref:System.Span%601>.

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

## <a name="byref-inref-and-outref"></a>ByRef Inref und outref

Es gibt drei Arten von `byref`:

* `inref<'T>`, einen verwalteten Zeiger zum Lesen von des zugrunde liegenden Werts.
* `outref<'T>`, einen verwalteten Zeiger zum Schreiben in den zugrunde liegenden Wert.
* `byref<'T>`, einen verwalteten Zeiger zum Lesen und schreiben den zugrunde liegenden Wert.

Ein `byref<'T>` übergeben werden kann, wobei ein `inref<'T>` wird erwartet. Auf ähnliche Weise eine `byref<'T>` übergeben werden kann, wobei ein `outref<'T>` wird erwartet.

## <a name="using-byrefs"></a>Verwenden von parametry

Verwenden einer `inref<'T>`, benötigen Sie einen Zeigerwert mit `&`:

```fsharp
open System

let f (dt: inref<DateTime>) =
    printfn "Now: %s" (dt.ToString())

let dt = DateTime.Now
f &dt // Pass a pointer to 'dt'
```

Um auf den Zeiger mit einem `outref<'T>` oder `byref<'T>`, achten Sie auch den Wert an, Sie nehmen einen Zeiger auf `mutable`.

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

Wenn Sie nur den Zeiger lesen, schreiben, sollten Sie `outref<'T>` anstelle von `byref<'T>`.

### <a name="inref-semantics"></a>Inref-Semantik

Betrachten Sie folgenden Code:

```fsharp
let f (x: inref<SomeStruct>) = s.SomeField
```

Semantisch gesehen bedeutet dies Folgendes:

* Der Inhaber des der `x` Zeiger kann nur verwenden, um den Wert zu lesen.
* Jeder beliebige Zeigertyp Sperre zum `struct` Felder geschachtelt `SomeStruct` erhalten Typ `inref<_>`.

Folgendes gilt auch:

* Es gibt keine Auswirkung, die von anderen Threads, oder Aliase haben keinen Schreibzugriff auf `x`.
* Es gibt keine Auswirkung, `SomeStruct` ist aufgrund des unveränderlich `x` wird ein `inref`.

Allerdings Wert für F#-Typen, die **sind** unveränderlich, die `this` Zeiger wird davon ausgegangen werden ein `inref`.

Alle diese Regeln, die zusammen bedeuten, dass den Inhaber des ein `inref` Zeiger kann nicht den unmittelbaren Inhalt des Arbeitsspeichers auf das gezeigt wird nicht ändern.

### <a name="outref-semantics"></a>Outref-Semantik

Der Zweck der `outref<'T>` ist, um anzugeben, dass der Zeiger nur aus gelesen werden sollen. Unerwartet `outref<'T>` zulässt, lesen den zugrunde liegenden Wert trotz seines Namens. Dies ist für die Kompatibilität. Semantisch gesehen sind `outref<'T>` funktioniert genauso wie `byref<'T>`.

### <a name="interop-with-c"></a>Interoperabilität mit c# #

C# unterstützt die `in ref` und `out ref` Schlüsselwörter, zusätzlich zu den `ref` zurückgibt. Die folgende Tabelle zeigt, wie f# interpretiert wie c# ausgibt:

|C#-Konstrukt|F#-leitet|
|------------|---------|
|`ref` Rückgabewert|`outref<'T>`|
|`ref readonly` Rückgabewert|`inref<'T>`|
|`in ref` Parameter|`inref<'T>`|
|`out ref` Parameter|`outref<'T>`|

Die folgende Tabelle zeigt, was f# ausgibt:

|F#-Konstrukts|Ausgegebene-Konstrukt|
|------------|-----------------|
|`inref<'T>` Argument|`[In]` Attribut für argument|
|`inref<'T>` zurück|`modreq` Attribut nach Wert|
|`inref<'T>` in abstrakten Slot oder Implementierung|`modreq` auf Argument- oder Rückgabetypen|
|`outref<'T>` Argument|`[Out]` Attribut für argument|

### <a name="type-inference-and-overloading-rules"></a>Typrückschluss und Überladen von Regeln

Ein `inref<'T>` Typ abgeleitet wird, vom F#-Compiler in den folgenden Fällen:

1. Ein .NET-Parameter oder Rückgabewert den Typ, der verfügt über eine `IsReadOnly` Attribut.
2. Die `this` Zeiger auf einen Strukturtyp, die keine änderbaren Felder enthält.
3. Die Adresse des Speicherorts im Arbeitsspeicher von einem anderen abgeleitet `inref<_>` Zeiger.

Wenn eine implizite Adresse eine `inref` ist erstellt wird, eine Überladung mit einem Argument des Typs `SomeType` wird empfohlen, eine Überladung mit einem Argument des Typs `inref<SomeType>`. Zum Beispiel:

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

In beiden Fällen die Überladungen, die die `System.DateTime` werden aufgelöst, anstatt die Überladungen, die die `inref<System.DateTime>`.

## <a name="byref-like-structs"></a>ByRef-ähnlichen Strukturen

Zusätzlich zu den `byref` / `inref` / `outref` Trio, Sie können Sie eigene Strukturen, die folgen können, definieren `byref`-Semantik wie. Dies erfolgt mit der <xref:System.Runtime.CompilerServices.IsByRefLikeAttribute> Attribut:

```fsharp
open System
open System.Runtime.CompilerServices

[<IsByRefLike; Struct>]
type S(count1: Span<int>, count2: Span<int>) =
    member x.Count1 = count1
    member x.Count2 = count2
```

`IsByRefLike` impliziert nicht `Struct`. Beide müssen für den Typ vorhanden sein.

Ein "`byref`-wie" "Struct" in f# ist ein Stack gebundene Wert. Sie wird nie auf dem verwalteten Heap zugewiesen. Ein `byref`-Struktur für Hochleistungs-Programmierung nützlich ist, wie sie mit leistungsfähiger Prüfungen zur Lebensdauer und nicht-Capture erzwungen wird. Die Regeln sind:

* Sie können verwendet werden Methodenrückgabe als Funktionsparameter, Methodenparameter, lokale Variablen.
* Sie können nicht statisch sein oder Instanzmember einer Klasse oder einer normalen Struktur.
* Sie können nicht anhand des Konstrukte Closure erfasst werden (`async` Methoden oder Lambdaausdrücke).
* Sie können nicht als generischer Parameter verwendet werden.

Dieser letzte Punkt ist entscheidend für F#-Programmierung im Pipeline-Stil, als `|>` ist eine generische Funktion, die die Eingabetypen parametrisiert. Diese Einschränkung gelockert werden kann, für die `|>` in Zukunft wird Inline und macht keine Aufrufe von nicht-generische Inlinefunktionen in ihrem Text.

Obwohl diese Regeln sehr stark Nutzung einzuschränken, werden diese zur Erfüllung der Zusage von High Performance computing, auf sichere Weise.

## <a name="byref-returns"></a>ByRef-Rückgaben

ByRef-Rückgaben von f#-Funktionen oder Elemente erstellt und verwendet werden können. Bei der Nutzung einer `byref`-Rückgabemethode, der Wert ist implizit keine Referenz. Zum Beispiel:

```fsharp
let safeSum(bytes: Span<byte>) =
    let mutable sum = 0
    for i in 0 .. bytes.Length - 1 do
        sum <- sum + int bytes.[i]
    sum

let sum = safeSum(mySpanOfBytes)
printfn "%d" sum // 'sum' is of type 'int'
```

Verwenden, um die implizite Dereferenzierung, z. B. übergeben einen Verweis über mehrere verkettete Aufrufe zu vermeiden `&x` (wobei `x` ist der Wert).

Sie können auch direkt auf eine Rückgabe zuweisen `byref`. Betrachten Sie das folgende Programm aus (dringend imperative):

```fsharp
type C() =
    let mutable nums = [| 1; 3; 7; 15; 31; 63; 127; 255; 511; 1023 |]

    override __.ToString() = String.Join(' ', nums)

    member __.FindLargestSmallerThan(target: int) =
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

## <a name="scoping-for-byrefs"></a>Festlegen des Gültigkeitsbereichs für parametry

Ein `let`-gebundener Wert sind keine seinen Verweis, der den Bereich überschreiten, in dem sie definiert wurde. Beispielsweise ist Folgendes nicht zulässig:

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

Dies verhindert, dass Sie andere Ergebnisse abhängig zu erhalten, bei der Kompilierung mit Optimierungen aktiviert oder deaktiviert.
