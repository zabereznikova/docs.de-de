---
title: Parameter und Argumente (F#)
description: Informationen Sie zu F#-sprachunterstützung zum Definieren von Parametern und übergeben von Argumenten an Funktionen, Methoden und Eigenschaften.
ms.date: 05/16/2016
ms.openlocfilehash: a1e2a70ca560bbb09d2cd10f47485cbe5c5e029d
ms.sourcegitcommit: 67de6cb5dd66a19f2180ba7e4d7aecc697f8a963
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2018
ms.locfileid: "44338258"
---
# <a name="parameters-and-arguments"></a>Parameter und Argumente

Dieses Thema beschreibt die sprachunterstützung zum Definieren von Parametern und übergeben von Argumenten an Funktionen, Methoden und Eigenschaften. Sie enthält Informationen zur Übergabe als Verweis, und wie Sie definieren und Verwenden von Methoden, die eine Variable Anzahl von Argumenten akzeptieren können.

## <a name="parameters-and-arguments"></a>Parameter und Argumente

Der Begriff *Parameter* wird verwendet, um die Namen für Werte beschreiben, die bereitgestellt werden sollen. Der Begriff *Argument* wird verwendet, für die Werte für jeden Parameter bereitgestellt.

Parameter können in Tupel oder Curry-Form oder in eine Kombination aus den beiden angegeben werden. Sie können mithilfe eines expliziten Parameternamens Argumente übergeben. Parameter der Methoden können als optional festgelegt und einen Standardwert angegeben werden.

## <a name="parameter-patterns"></a>Parametermuster

Parameter, Funktionen und Methoden bereitgestellt sind, im allgemeinen Mustern, die durch Leerzeichen getrennt. Dies bedeutet, dass im Prinzip die Muster in beschrieben [Vergleichsausdrücke](match-expressions.md) in einer Parameterliste für eine Funktion oder Member verwendet werden können.

In der Regel verwenden Sie Methoden Tupelform übergeben von Argumenten. Dies wird ein besseres Ergebnis aus der Perspektive der anderen erreicht, da die Tupelform wie übereinstimmt, die Argumente in .NET Methoden übergeben werden.

Die Curry-Form wird meistens verwendet, mit Funktionen, die mithilfe von erstellt `let` Bindungen.

Der folgende Pseudocode zeigt Beispiele für Tupel und Curry-Argumente.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Kombinierte Formen sind möglich, wenn einige Argumente im Tupel sind und einige nicht.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Andere Muster können auch verwendet werden, in der Parameterliste, aber wenn das Muster der Parameter nicht alle Mögliche Eingaben übereinstimmt, gibt es möglicherweise eine unvollständige Übereinstimmung zur Laufzeit. Die Ausnahme `MatchFailureException` wird generiert, wenn der Wert eines Arguments nicht die in der Parameterliste angegebenen Mustern übereinstimmt. Der Compiler gibt eine Warnung, wenn ein Muster für die Parameter nach unvollständigen Übereinstimmungen zulässt. Mindestens eine andere Muster ist häufig nützlich für Parameterlisten, und das ist das Platzhaltermuster. Sie verwenden das Platzhaltermuster in einer Parameterliste, wenn Sie möchten einfach alle Argumente ignorieren, die bereitgestellt werden. Der folgende Code veranschaulicht die Verwendung des Platzhaltermusters in einer Argumentliste.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

Das Platzhaltermuster kann sein, hilfreich, wenn Sie nicht, die übergebenen Argumenten benötigen, z. B. den Haupteinstiegspunkt für ein Programm, wenn Sie nicht die Befehlszeilenargumente interessiert sind, die normalerweise als Zeichenfolgenarray, wie im folgenden Code bereitgestellt werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Sind andere Muster, die in-Argumente verwendet werden die `as` Muster und Bezeichnermuster Unterscheidungs-Unions und aktive Muster zugeordnet. Sie können wie folgt die Einzelfall-Unterscheidungs-union-Muster verwenden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

Die Ausgabe lautet wie folgt.

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

Mit aktiven Mustern können als Parameter, z. B. nützlich bei der Transformation ein Argument in einem gewünschten Format wie im folgenden Beispiel gezeigt:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

Sie können die `as` Muster, um einen übereinstimmenden Wert als ein lokaler Wert zu speichern, wie in der folgenden Zeile des Codes angezeigt wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Ein weiteres Muster, das gelegentlich verwendet werden, ist eine Funktion, die das letzte Argument bereitstellen, als Text der Funktion unbenannte verlässt, ein Lambda-Ausdruck, der die implizite Argument sofort eine Musterübereinstimmung ausführt. Ein Beispiel hierfür ist die folgende Codezeile.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Dieser Code definiert eine Funktion, die eine generische Liste annimmt und zurückgibt `true` ist die Liste leer ist, und `false` andernfalls. Die Verwendung solcher Techniken betrachtet möglich Code schwieriger zu lesen.

In einigen Fällen Muster, bei denen unvollständige Übereinstimmungen sind nützlich, z. B. Wenn Sie wissen, dass die Listen in Ihrem Programm nur drei Elemente verfügen, können ein Muster wie folgt in einer Parameterliste.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

Die Verwendung von Mustern, die unvollständige Übereinstimmungen ist am besten für die schnelle Erstellung von Prototypen und andere temporäre Zwecke reserviert. Der Compiler gibt eine Warnung für diese Art von Code. Solche Muster nicht grundsätzlich alle möglichen Eingaben abdecken und sind daher nicht für die Komponenten-APIs geeignet ist.

## <a name="named-arguments"></a>Benannte Argumente

Argumente für Methoden Position in einer Argumentliste von durch Trennzeichen getrennte angegeben werden können, oder sie können übergeben werden an eine Methode explizit durch Eingabe des Namens, gefolgt von einem Gleichheitszeichen und dem Wert übergeben werden. Wenn angegeben, indem Sie den Namen angeben, können sie in einer anderen Reihenfolge aus, die verwendet werden, in der Deklaration angezeigt werden.

Benannte Argumente können Code besser lesbar und besser anpassen auf bestimmte Arten von Änderungen in der API, z. B. eine neuanordnung der Parameter der Methode zu machen.

Benannte Argumente dürfen nur für Methoden, nicht für `let`-gebunden, Funktionen, Werte von Funktionen oder Lambda-Ausdrücke.

Das folgende Codebeispiel veranschaulicht die Verwendung von benannten Argumente.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

In einem Aufruf für einen Klassenkonstruktor können Sie die Werte der Eigenschaften der Klasse mit einer Syntax wie mit der benannten Argumente festlegen. Das folgende Beispiel zeigt diese Syntax.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Weitere Informationen finden Sie unter [Konstruktoren (f#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Optionale Parameter

Sie können einen optionalen Parameter für eine Methode mit einem Fragezeichen angegeben vor den Parameternamen angeben. Optionale Parameter wie der F#-Option-Typ, interpretiert werden, damit Sie auf die übliche Weise abgefragt werden können, dass Optionstypen, mithilfe abgefragt werden einer `match` Ausdruck mit `Some` und `None`. Optionale Parameter sind zulässig, nur für Elemente, die nicht auf Funktionen, die mithilfe von erstellt `let` Bindungen.

Sie können auch eine Funktion `defaultArg`, wodurch einen Standardwert eines optionalen Arguments festgelegt. Die `defaultArg` Funktion akzeptiert den optionalen Parameter als erstes Argument und der Standardwert als das zweite.

Das folgende Beispiel veranschaulicht die Verwendung der optionalen Parameter.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

Die Ausgabe lautet wie folgt.

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a>Übergeben als Verweis

Übergeben einen F#-Wert als Verweis umfasst [Byrefs](byrefs.md), die verwaltete Zeigertypen sind. Anleitung für die zu verwendende Typ wie folgt lautet:

* Verwendung `inref<'T>` , wenn Sie nur den Zeiger lesen müssen.
* Verwendung `outref<'T>` , wenn Sie nur auf den Zeiger schreiben müssen.
* Verwendung `byref<'T>` Wenn müssen Sie sowohl auslesen und Schreiben in den Zeiger.

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

Da der Parameter ein Zeiger ist, und der Wert kann geändert werden, werden alle Änderungen an den Wert nach der Ausführung der Funktion beibehalten.

Sie können ein Tupel als Rückgabewert einer speichern `out` Parameter in .NET-Methoden-Bibliothek. Alternativ können Sie behandeln die `out` Parameter als ein `byref` Parameter. Im folgenden Codebeispiel wird veranschaulicht, in beide Richtungen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Parameterarrays

Gelegentlich ist es erforderlich, eine Funktion zu definieren, die eine beliebige Anzahl von Parametern heterogenen Typs akzeptiert. Es wäre nicht sehr praktisch, erstellen alle möglichen überladenen Methoden um für alle Typen zu berücksichtigen, die verwendet werden können. Die .NET Implementierungen bieten Unterstützung für solche Methoden über die Parameter-Array-Funktion. Eine Methode, die ein Parameterarray in der Signatur verwendet, werden, kann mit einer beliebigen Anzahl von Parametern angegeben werden. Die Parameter werden in ein Array eingefügt. Der Typ der Elemente des Arrays bestimmt die Parametertypen, die an die Funktion übergeben werden können. Wenn Sie das Parameterarray mit definieren `System.Object` als Typ des Elements, klicken Sie dann Clientcode kann Werte übergeben eines beliebigen Typs.

In f# können Parameterarrays nur in Methoden definiert werden. Sie können nicht verwendet werden, in der eigenständigen oder Funktionen, die in Modulen definiert sind.

Sie definieren ein Parameterarray mithilfe der `ParamArray` Attribut. Die `ParamArray` Attribut kann nur auf den letzten Parameter angewendet werden.

Der folgende Code veranschaulicht beide eine .NET-Methode übergeben wird, die ein Parameterarray und die Definition eines Typs in f# verwendet wird, die eine Methode, die akzeptiert ein Parameterarray aufrufen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Wenn in einem Projekt ausführen, lautet die Ausgabe des obigen Codes wie folgt:

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

- [Mitglieder](members/index.md)
