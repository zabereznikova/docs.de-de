---
title: Parameter und Argumente
description: Erfahren Sie mehr über die Sprachunterstützung von F- zum Definieren von Parametern und Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften.
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401052"
---
# <a name="parameters-and-arguments"></a>Parameter und Argumente

In diesem Thema wird die Sprachunterstützung zum Definieren von Parametern und Übergeben von Argumenten an Funktionen, Methoden und Eigenschaften beschrieben. Sie enthält Informationen zum Übergeben von Verweis und zum Definieren und Verwenden von Methoden, die eine variable Anzahl von Argumenten annehmen können.

## <a name="parameters-and-arguments"></a>Parameter und Argumente

Der *Begriffparameter* wird verwendet, um die Namen für Werte zu beschreiben, die voraussichtlich angegeben werden. Das *Termargument* wird für die für jeden Parameter bereitgestellten Werte verwendet.

Parameter können in Tupel- oder Curryform oder in einer Kombination aus beiden angegeben werden. Sie können Argumente übergeben, indem Sie einen expliziten Parameternamen verwenden. Parameter von Methoden können als optional angegeben und mit einem Standardwert angegeben werden.

## <a name="parameter-patterns"></a>Parametermuster

Parameter, die Funktionen und Methoden zur Verfügung gestellt werden, sind im Allgemeinen Muster, die durch Leerzeichen getrennt sind. Dies bedeutet, dass grundsätzlich jedes der in [Match Expressions](match-expressions.md) beschriebenen Muster in einer Parameterliste für eine Funktion oder einen Member verwendet werden kann.

Methoden verwenden in der Regel die Tupelform des Übergebens von Argumenten. Dies führt zu einem klareren Ergebnis aus der Perspektive anderer .NET-Sprachen, da das Tupelformular mit der Art und Weise übereinstimmt, wie Argumente in .NET-Methoden übergeben werden.

Das Curry-Formular wird am häufigsten mit `let` Funktionen verwendet, die mithilfe von Bindungen erstellt werden.

Der folgende Pseudocode zeigt Beispiele für Tupel- und Curry-Argumente.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Kombinierte Formulare sind möglich, wenn einige Argumente in Tupeln sind und einige nicht.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Andere Muster können auch in Parameterlisten verwendet werden, aber wenn das Parametermuster nicht mit allen möglichen Eingaben übereinstimmt, kann es zur Laufzeit zu einer unvollständigen Übereinstimmung führen. Die `MatchFailureException` Ausnahme wird generiert, wenn der Wert eines Arguments nicht mit den in der Parameterliste angegebenen Mustern übereinstimmt. Der Compiler gibt eine Warnung aus, wenn ein Parametermuster unvollständige Übereinstimmungen zulässt. Mindestens ein anderes Muster ist häufig für Parameterlisten nützlich, und das ist das Platzhaltermuster. Sie verwenden das Platzhaltermuster in einer Parameterliste, wenn Sie einfach alle angegebenen Argumente ignorieren möchten. Der folgende Code veranschaulicht die Verwendung des Platzhaltermusters in einer Argumentliste.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

Das Platzhaltermuster kann nützlich sein, wenn Sie die übergebenen Argumente nicht benötigen, z. B. im Haupteinstiegspunkt an ein Programm, wenn Sie nicht an den Befehlszeilenargumenten interessiert sind, die normalerweise als Zeichenfolgenarray bereitgestellt werden, wie im folgenden Code.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Andere Muster, die manchmal in `as` Argumenten verwendet werden, sind das Muster und Bezeichnermuster, die mit diskriminierten Gewerkschaften und aktiven Mustern verbunden sind. Sie können das einzelne diskriminierte Union-Muster wie folgt verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

Die Ausgabe lautet wie folgt.

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

Aktive Muster können als Parameter nützlich sein, z. B. beim Transformieren eines Arguments in ein gewünschtes Format, wie im folgenden Beispiel:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

Sie können `as` das Muster verwenden, um einen übereinstimmenden Wert als lokalen Wert zu speichern, wie in der folgenden Codezeile dargestellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Ein anderes Muster, das gelegentlich verwendet wird, ist eine Funktion, die das letzte Argument unbenannt lässt, indem als Text der Funktion ein Lambda-Ausdruck bereitstellt, der sofort eine Musterübereinstimmung für das implizite Argument ausführt. Ein Beispiel hierfür ist die folgende Codezeile.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Dieser Code definiert eine Funktion, die `true` eine generische Liste annimmt und zurückgibt, wenn die Liste leer ist, und `false` auf andere Weise. Die Verwendung solcher Techniken kann das Lesen von Code erschweren.

Gelegentlich sind Muster, die unvollständige Übereinstimmungen beinhalten, nützlich, z. B. wenn Sie wissen, dass die Listen in Ihrem Programm nur drei Elemente enthalten, können Sie ein Muster wie das folgende in einer Parameterliste verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

Die Verwendung von Mustern, die unvollständige Übereinstimmungen aufweisen, ist am besten für schnelles Prototyping und andere temporäre Verwendungen reserviert. Der Compiler gibt eine Warnung für diesen Code aus. Solche Muster können nicht den allgemeinen Fall aller möglichen Eingänge abdecken und sind daher nicht für Komponenten-APIs geeignet.

## <a name="named-arguments"></a>Benannte Argumente

Argumente für Methoden können durch Position in einer durch Kommas getrennten Argumentliste angegeben werden, oder sie können explizit an eine Methode übergeben werden, indem der Name angegeben wird, gefolgt von einem Gleichheitszeichen und dem wert, der übergeben werden soll. Wenn sie durch Angabe des Namens angegeben werden, können sie in einer anderen Reihenfolge als in der Deklaration angezeigt werden.

Benannte Argumente können Code lesbarer und anpassungsfähiger für bestimmte Arten von Änderungen in der API machen, z. B. eine Neuanordnung von Methodenparametern.

Benannte Argumente sind nur für `let`Methoden zulässig, nicht für -bound-Funktionen, Funktionswerte oder Lambda-Ausdrücke.

Im folgenden Codebeispiel wird die Verwendung benannter Argumente veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

In einem Aufruf eines Klassenkonstruktors können Sie die Werte der Eigenschaften der Klasse festlegen, indem Sie eine Syntax verwenden, die der von benannten Argumenten ähnelt. Das folgende Beispiel zeigt diese Syntax.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Weitere Informationen finden Sie unter [Konstruktoren (F)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Optionale Parameter

Sie können einen optionalen Parameter für eine Methode angeben, indem Sie ein Fragezeichen vor dem Parameternamen verwenden. Optionale Parameter werden als Optionstyp "F" interpretiert, sodass Sie sie auf die `match` reguläre `Some` Art `None`und Weise abfragen können, dass Optionstypen abgefragt werden, indem Sie einen Ausdruck mit und verwenden. Optionale Parameter sind nur für Member zulässig, nicht für Funktionen, die mithilfe `let` von Bindungen erstellt wurden.

Sie können vorhandene optionale Werte nach Parametername an die Methode übergeben, z. `?arg=None` B. oder `?arg=Some(3)` oder `?arg=arg`. Dies kann nützlich sein, wenn Sie eine Methode erstellen, die optionale Argumente an eine andere Methode übergibt.

Sie können auch `defaultArg`eine Funktion verwenden, die einen Standardwert eines optionalen Arguments festlegt. Die `defaultArg` Funktion nimmt den optionalen Parameter als erstes Argument und den Standardwert als zweites.

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

Für die Zwecke des Interops "C" und `[<Optional; DefaultParameterValue<(...)>]` des Visual Basic-Interops können Sie die Attribute in F- verwenden, sodass Aufrufer ein Argument als optional anzeigen. Dies entspricht dem Definieren des Arguments als `MyMethod(int i = 3)`optional in C- wie in .

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

Sie können auch ein neues Objekt als Standardparameterwert angeben. Das `Foo` Element kann z. `CancellationToken` B. eine optionale Eingabe als Eingabe haben:

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

Der Wert, der `DefaultParameterValue` als Argument angegeben wird, muss mit dem Typ des Parameters übereinstimmen. Das Folgende ist z. B. nicht zulässig:

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

In diesem Fall generiert der Compiler eine Warnung und ignoriert beide Attribute vollständig. Beachten Sie, `null` dass der Standardwert typannotiert werden muss, da der Compiler andernfalls `[<Optional; DefaultParameterValue(null:obj)>] o:obj`den falschen Typ ableitet, d. h. .

## <a name="passing-by-reference"></a>Vorbeianreise durch Referenz

Das Übergeben eines F-Werts als Verweis umfasst [byrefs](byrefs.md), die verwaltete Zeigertypen sind. Anleitung für den typ, der verwendet werden soll, lautet wie folgt:

- Verwenden `inref<'T>` Sie diese Datei, wenn Sie nur den Zeiger lesen müssen.
- Verwenden `outref<'T>` Sie diese Datei, wenn Sie nur in den Zeiger schreiben müssen.
- Verwenden `byref<'T>` Sie diese Verwendung, wenn Sie sowohl aus dem Zeiger lesen als auch in den Zeiger schreiben müssen.

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

Da der Parameter ein Zeiger ist und der Wert veränderbar ist, werden alle Änderungen am Wert nach der Ausführung der Funktion beibehalten.

Sie können ein Tupel als Rückgabewert `out` verwenden, um alle Parameter in .NET-Bibliotheksmethoden zu speichern. Alternativ können Sie den `out` Parameter `byref` auch als Parameter behandeln. Das folgende Codebeispiel veranschaulicht beide Möglichkeiten.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Parameterarrays

Gelegentlich ist es notwendig, eine Funktion zu definieren, die eine beliebige Anzahl von Parametern heterogenen Typs annimmt. Es wäre nicht praktikabel, alle möglichen überladenen Methoden zu erstellen, um alle Typen zu berücksichtigen, die verwendet werden könnten. Die .NET-Implementierungen unterstützen solche Methoden über das Parameterarray-Feature. Eine Methode, die ein Parameterarray in ihrer Signatur übernimmt, kann mit einer beliebigen Anzahl von Parametern bereitgestellt werden. Die Parameter werden in ein Array eingefügt. Der Typ der Arrayelemente bestimmt die Parametertypen, die an die Funktion übergeben werden können. Wenn Sie das Parameterarray mit `System.Object` als Elementtyp definieren, kann Clientcode Werte eines beliebigen Typs übergeben.

Parameterarrays können nur in Methoden definiert werden. Sie können nicht in eigenständigen Funktionen oder Funktionen verwendet werden, die in Modulen definiert sind.

Sie definieren ein Parameterarray `ParamArray` mithilfe des Attributs. Das `ParamArray` Attribut kann nur auf den letzten Parameter angewendet werden.

Der folgende Code veranschaulicht sowohl das Aufrufen einer .NET-Methode, die ein Parameterarray verwendet, als auch die Definition eines Typs in F, der über eine Methode verfügt, die ein Parameterarray verwendet.

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Bei Der Ausführung in einem Projekt wird der vorherige Code wie folgt ausgegeben:

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>Weitere Informationen

- [Mitglieder](./members/index.md)
