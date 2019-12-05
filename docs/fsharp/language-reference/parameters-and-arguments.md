---
title: Parameter und Argumente
description: Erfahren Sie F# mehr über die Sprachunterstützung zum Definieren von Parametern und zum Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften.
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837128"
---
# <a name="parameters-and-arguments"></a>Parameter und Argumente

In diesem Thema wird die Sprachunterstützung für das Definieren von Parametern und das Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften beschrieben. Sie enthält Informationen zum übergeben als Verweis und zum Definieren und Verwenden von Methoden, die eine Variable Anzahl von Argumenten annehmen können.

## <a name="parameters-and-arguments"></a>Parameter und Argumente

Der Term- *Parameter* wird verwendet, um die Namen für Werte zu beschreiben, die bereitgestellt werden sollen. Das Begriffs *Argument* wird für die Werte verwendet, die für jeden Parameter bereitgestellt werden.

Parameter können in einem Tupel-oder Curry-Formular oder in einer Kombination der beiden Werte angegeben werden. Sie können Argumente übergeben, indem Sie einen expliziten Parameternamen verwenden. Parameter von Methoden können als optional und mit einem Standardwert angegeben werden.

## <a name="parameter-patterns"></a>Parameter Muster

Parameter, die für Funktionen und Methoden bereitgestellt werden, sind im Allgemeinen durch Leerzeichen getrennte Muster. Dies bedeutet, dass im Prinzip jedes der in [Match Expressions](match-expressions.md) beschriebenen Muster in einer Parameterliste für eine Funktion oder ein Member verwendet werden kann.

Methoden verwenden normalerweise die tupelform der Übergabe von Argumenten. Dadurch wird ein deutlicheres Ergebnis aus der Perspektive anderer .NET-Sprachen erzielt, da das tupelformular mit der Art und Weise übereinstimmt, in der die Argumente in .NET-Methoden

Das Curry-Formular wird am häufigsten mit Funktionen verwendet, die mit `let` Bindungen erstellt wurden.

Der folgende Pseudo Code zeigt Beispiele für Tupel-und Curry-Argumente.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Kombinierte Formulare sind möglich, wenn sich einige Argumente in Tupeln befinden und andere nicht.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Andere Muster können auch in Parameterlisten verwendet werden, aber wenn das Parameter Muster nicht allen möglichen Eingaben entspricht, gibt es möglicherweise eine unvollständige Entsprechung zur Laufzeit. Die Ausnahme `MatchFailureException` wird generiert, wenn der Wert eines Arguments nicht mit den in der Parameterliste angegebenen Mustern identisch ist. Der Compiler gibt eine Warnung aus, wenn ein Parameter Muster unvollständige Übereinstimmungen zulässt. Mindestens ein anderes Muster ist häufig für Parameterlisten nützlich, und das ist das Platzhalter Muster. Sie verwenden das Platzhalter Muster in einer Parameterliste, wenn Sie einfach alle angegebenen Argumente ignorieren möchten. Der folgende Code veranschaulicht die Verwendung des Platzhalter Musters in einer Argumentliste.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

Das Platzhalter Muster kann nützlich sein, wenn Sie die übergebenen Argumente nicht benötigen, z. b. im Haupteinstiegspunkt an ein Programm, wenn Sie nicht an den Befehlszeilen Argumenten interessiert sind, die normalerweise als Zeichen folgen Array bereitgestellt werden, wie im folgenden Code.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Andere Muster, die manchmal in Argumenten verwendet werden, sind das `as` Muster und bezeichnermuster, die mit diskriminierten Unions und aktiven Mustern verknüpft sind. Sie können das Union-Muster mit einem einzelnen Fall wie folgt verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

Die Ausgabe lautet wie folgt.

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

Aktive Muster können als Parameter nützlich sein, z. b. beim Transformieren eines Arguments in ein gewünschtes Format, wie im folgenden Beispiel gezeigt:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

Sie können das `as` Muster verwenden, um einen übereinstimmenden Wert als lokalen Wert zu speichern, wie in der folgenden Codezeile dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Ein anderes Muster, das gelegentlich verwendet wird, ist eine Funktion, die das Letzte unbenannte Argument verlässt, indem als Text der Funktion ein Lambda-Ausdruck bereitgestellt wird, der sofort eine Muster Übereinstimmung für das implizite Argument ausführt. Ein Beispiel hierfür ist die folgende Codezeile.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Dieser Code definiert eine Funktion, die eine generische Liste annimmt und `true` zurückgibt, wenn die Liste leer ist, und `false` andernfalls. Die Verwendung solcher Techniken kann das Lesen des Codes erschweren.

Gelegentlich sind Muster mit unvollständigen Übereinstimmungen nützlich, wenn Sie z. b. wissen, dass die Listen im Programm nur drei Elemente enthalten, können Sie ein Muster wie das folgende in einer Parameterliste verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

Die Verwendung von Mustern mit unvollständigen Übereinstimmungen ist am besten für die schnelle Prototyperstellung und andere temporäre Verwendungszwecke reserviert. Der Compiler gibt eine Warnung für diesen Code aus. Solche Muster können nicht den allgemeinen Fall aller möglichen Eingaben abdecken und sind daher nicht für Komponenten-APIs geeignet.

## <a name="named-arguments"></a>Benannte Argumente

Argumente für Methoden können durch die Position in einer durch Trennzeichen getrennten Argumentliste angegeben werden, oder Sie können explizit an eine Methode durch Angabe des Namens, gefolgt von einem Gleichheitszeichen und dem zu über gebenden Wert weitergeleitet werden. Wenn Sie durch Angabe des Namens angegeben werden, können Sie in einer anderen Reihenfolge als der in der Deklaration verwendeten angezeigt werden.

Benannte Argumente können den Code besser lesbar machen und besser an bestimmte Typen von Änderungen in der API angepasst werden, z. b. eine Neuanordnung von Methoden Parametern.

Benannte Argumente sind nur für Methoden, nicht für `let`gebundene Funktionen, Funktions Werte oder Lambda Ausdrücke zulässig.

Im folgenden Codebeispiel wird die Verwendung von benannten Argumenten veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

In einem-Klassenkonstruktor können Sie die Werte der Eigenschaften der-Klasse festlegen, indem Sie eine Syntax verwenden, die dem von benannten Argumenten ähnelt. Das folgende Beispiel zeigt diese Syntax.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Weitere Informationen finden Sie unter [Konstruktoren (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Optionale Parameter

Sie können einen optionalen Parameter für eine Methode angeben, indem Sie ein Fragezeichen vor dem Parameternamen verwenden. Optionale Parameter werden als F# Optionstyp interpretiert, sodass Sie Sie in regulärer Weise Abfragen können, indem Sie einen `match` Ausdruck mit `Some` und `None`verwenden. Optionale Parameter sind nur für Member zulässig, nicht für Funktionen, die mit `let` Bindungen erstellt wurden.

Sie können vorhandene optionale Werte an eine Methode übergeben, indem Sie den Parameternamen angeben, z. b. `?arg=None` oder `?arg=Some(3)` oder `?arg=arg`. Dies kann bei der Erstellung einer Methode nützlich sein, die optionale Argumente an eine andere Methode übergibt.

Sie können auch eine Funktion `defaultArg`verwenden, mit der ein Standardwert eines optionalen Arguments festgelegt wird. Die `defaultArg`-Funktion übernimmt den optionalen-Parameter als erstes Argument und den Standardwert als zweiten.

Das folgende Beispiel veranschaulicht die Verwendung optionaler Parameter.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

Die Ausgabe lautet wie folgt.

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

Im Hinblick auf C# und Visual Basic Interop können Sie die in F#`[<Optional; DefaultParameterValue<(...)>]` Attribute verwenden, damit Aufrufer ein Argument als optional sehen. Dies entspricht der Definition des Arguments als optional in C# wie in `MyMethod(int i = 3)`.

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

Sie können auch ein neues-Objekt als Standardparameter Wert angeben. Beispielsweise könnte das `Foo`-Element über einen optionalen `CancellationToken` als Eingabe verfügen:

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

Der als Argument für `DefaultParameterValue` angegebene Wert muss mit dem Typ des Parameters identisch sein. Beispielsweise ist Folgendes nicht zulässig:

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

In diesem Fall generiert der Compiler eine Warnung und ignoriert beide Attribute vollständig. Beachten Sie, dass der Standardwert `null` vom Typ mit Anmerkungen versehen werden muss, da der Compiler andernfalls den falschen Typ, d. h. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`, anleitet.

## <a name="passing-by-reference"></a>Übergeben als Verweis

Das übergeben F# eines Werts als Verweis umfasst [ByRefs](byrefs.md), bei denen es sich um verwaltete Zeiger Typen handelt. Der zu verwendende Typ lautet wie folgt:

- Verwenden Sie `inref<'T>`, wenn Sie nur den Zeiger lesen müssen.
- Verwenden Sie `outref<'T>`, wenn Sie nur in den Zeiger schreiben müssen.
- Verwenden Sie `byref<'T>`, wenn Sie sowohl Lese-als auch Schreibzugriff auf den Zeiger benötigen.

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

Da der-Parameter ein Zeiger ist und der Wert änderbar ist, werden alle Änderungen am Wert nach der Ausführung der Funktion beibehalten.

Sie können ein Tupel als Rückgabewert verwenden, um beliebige `out` Parameter in .net-Bibliotheks Methoden zu speichern. Alternativ können Sie den `out`-Parameter als `byref` Parameter behandeln. Im folgenden Codebeispiel werden beide Methoden veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Parameterarrays

Gelegentlich ist es erforderlich, eine Funktion zu definieren, die eine beliebige Anzahl von Parametern des heterogenen Typs annimmt. Es wäre nicht praktikabel, alle möglichen überladenen Methoden zu erstellen, um alle Typen zu berücksichtigen, die verwendet werden könnten. Die .net-Implementierungen unterstützen solche Methoden durch das Parameter Array Feature. Eine Methode, die ein Parameter Array in der Signatur annimmt, kann mit einer beliebigen Anzahl von Parametern bereitgestellt werden. Die Parameter werden in einem Array abgelegt. Der Typ der Array Elemente bestimmt die Parametertypen, die an die Funktion übergeben werden können. Wenn Sie das Parameter Array mit `System.Object` als Elementtyp definieren, kann der Client Code Werte eines beliebigen Typs übergeben.

In F# können Parameterarrays nur in Methoden definiert werden. Sie können nicht in eigenständigen Funktionen oder Funktionen verwendet werden, die in Modulen definiert sind.

Ein Parameter Array wird mit dem `ParamArray`-Attribut definiert. Das `ParamArray`-Attribut kann nur auf den letzten Parameter angewendet werden.

Der folgende Code veranschaulicht beide eine .NET-Methode übergeben wird, die ein Parameterarray und die Definition eines Typs in F# verwendet wird, die eine Methode, die akzeptiert ein Parameterarray aufrufen.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Wenn Sie in einem Projekt ausführen, lautet die Ausgabe des vorherigen Codes wie folgt:

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>Siehe auch

- [Mitglieder](./members/index.md)
