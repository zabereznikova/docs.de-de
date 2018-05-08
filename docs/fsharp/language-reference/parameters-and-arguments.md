---
title: Parameter und Argumente (F#)
description: Informationen Sie zu F#-sprachunterstützung für das Definieren von Parametern und übergeben von Argumenten zu Funktionen, Methoden und Eigenschaften.
ms.date: 05/16/2016
ms.openlocfilehash: 319cf0e7346d498ce34e41a9993fe0160038461a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="parameters-and-arguments"></a>Parameter und Argumente

Dieses Thema beschreibt die sprachunterstützung für das Definieren von Parametern und übergeben von Argumenten zu Funktionen, Methoden und Eigenschaften. Es enthält Informationen über das als Verweis übergeben und das Definieren und Verwenden von Methoden, die eine Variable Anzahl von Argumenten akzeptieren können.


## <a name="parameters-and-arguments"></a>Parameter und Argumente
Der Begriff *Parameter* wird verwendet, um die Namen für die Werte zu beschreiben, die bereitgestellt werden soll. Der Begriff *Argument* wird verwendet, für die Werte für jeden Parameter bereitgestellt.

Parameter können in Tupel oder Curry-Form oder in einer Kombination von beiden angegeben werden. Sie können Argumente übergeben, indem Sie eine explizite Parameternamen. Parameter der Methoden können als optional angegeben und einen Standardwert angegeben werden.


## <a name="parameter-patterns"></a>Parametermuster
Funktionen und Methoden eingegebenen Parameter sind im allgemeinen Mustern, die durch Leerzeichen getrennt an. Dies bedeutet, dass im Prinzip die Muster beschrieben [Übereinstimmungsausdrücken](match-expressions.md) für eine Funktion oder ein Element in einer Parameterliste verwendet werden können.

In der Regel verwenden Sie Methoden Tupelform übergeben von Argumenten. Dadurch wird ein besseres Ergebnis aus der Perspektive eines anderen erreicht, da die Tupelform wie übereinstimmt, die in .NET-Methoden Argumente übergeben werden.

Die Curry-Form werden am häufigsten verwendet, mit Funktionen, die mithilfe von erstellt `let` Bindungen.

Der folgende Pseudocode zeigt Beispiele für Tupel und Curry-Argumente.

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

Kombinierte Formen sind möglich, wenn einige Argumente in Tupeln sind und einige nicht.

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

Andere Muster können auch in Parameterlisten verwendet werden, aber wenn das Muster der Parameter nicht alle Mögliche Eingaben übereinstimmt, gibt es möglicherweise eine unvollständige Übereinstimmung zur Laufzeit. Die Ausnahme `MatchFailureException` wird generiert, wenn der Wert eines Arguments nicht die in der Parameterliste angegebenen Mustern übereinstimmt. Der Compiler einer Warnung, wenn ein Muster für die Parameter für unvollständige Übereinstimmungen zulässt. Mindestens eine andere Muster ist häufig hilfreich für Parameterlisten und, die das Platzhaltermuster wird. Sie verwenden das Platzhaltermuster in einer Parameterliste, wenn einfach ignorieren keine Argumente, die bereitgestellt werden sollen. Der folgende Code veranschaulicht die Verwendung des Platzhaltermusters in einer Argumentliste.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

Das Platzhaltermuster kann hilfreich, wenn Sie die übergebenen Argumente nicht benötigen, z. B. den Haupteinstiegspunkt für ein Programm sein, wenn Sie nicht die Befehlszeilenargumente interessiert sind, die normalerweise als ein Array von Zeichenfolgen, wie im folgenden Code angegeben werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

Sind andere Muster, die in-Argumente verwendet werden die `as` Muster und Bezeichnermuster Unterscheidungs-Unions und aktive Muster zugeordnet. Sie können die einzelnen Fall Unterscheidungs-union-Muster wie folgt verwenden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

Die Ausgabe lautet wie folgt.

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

Aktive Muster können als Parameter, z. B. hilfreich sein, die bei der Transformation ein Argument in einem gewünschten Format, wie im folgenden Beispiel gezeigt:

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

Sie können die `as` Muster, um einen übereinstimmenden Wert als einen lokalen Wert zu speichern, wie in der folgenden Zeile des Codes dargestellt wird.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

Ein anderes Muster, das gelegentlich verwendet wird, ist eine Funktion, die bewirkt, das letzte Argument unbenannte dass bereitstellen, wie der Text der Funktion, ein Lambda-Ausdruck, der sofort einen Mustervergleich für das implizite Argument ausführt. Ein Beispiel hierfür ist die folgende Codezeile.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

Dieser Code definiert eine Funktion, die eine generische Liste akzeptiert und gibt `true` Wenn die Liste leer ist und `false` andernfalls. Die Verwendung solcher Techniken vererbungsoptionen Code schwieriger zu lesen.

In einigen Fällen eignen sich Muster, die unvollständige Übereinstimmungen einschließen, z. B. Wenn Sie wissen, dass die Listen in Ihrem Programm nur drei Elemente verfügen, können ein Muster wie folgt in einer Parameterliste.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

Die Verwendung von Mustern, die unvollständig übereinstimmenden ist am besten für schnellen Prototyping und andere temporäre Verwendung reserviert. Der Compiler wird einer Warnung für diesen Code. Muster dieser Art können nicht im allgemeinen Fall alle möglichen Eingaben behandelt und sind daher nicht für die Komponente APIs geeignet ist.

## <a name="named-arguments"></a>Benannte Argumente
Argumente für Methoden können anhand der Position in einer durch Trennzeichen getrennte Argumentliste angegeben werden, oder sie können übergeben werden an eine Methode explizit durch Eingabe des Namens, gefolgt von einem Gleichheitszeichen und dem Wert übergeben werden muss. Wenn angegeben, indem Sie den Namen angeben, können sie in einer anderen Reihenfolge aus, die in der Deklaration verwendet angezeigt.

Benannte Argumente können Code besser lesbar und mehr anwendbare bestimmter Arten von Änderungen in der API, z. B. eine neuanordnung der Parameter der Methode vornehmen.

Benannte Argumente dürfen nur für Methoden, nicht für `let`-Funktionen, Funktionswerte oder Lambda-Ausdrücke gebunden.

Das folgende Codebeispiel veranschaulicht die Verwendung von benannten Argumenten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

In einem Aufruf für einen Klassenkonstruktor können Sie die Werte der Eigenschaften der Klasse mit einer Syntax ähnelt der von benannten Argumenten festlegen. Das folgende Beispiel zeigt diese Syntax.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

Weitere Informationen finden Sie unter [Konstruktoren (f#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).

## <a name="optional-parameters"></a>Optionale Parameter
Sie können einen optionalen Parameter für eine Methode mit einem Fragezeichen vor den Namen des Parameters angeben. Optionale Parameter als F#-Optionstyp interpretiert werden, damit Sie auf die übliche Weise abgefragt werden können, dass Optionstypen, mithilfe abgefragt werden einer `match` Ausdruck mit `Some` und `None`. Optionale Parameter dürfen nur für Elemente, nicht auf Funktionen, die mithilfe von erstellt `let` Bindungen.

Sie können auch eine Funktion `defaultArg`, der einen Standardwert eines optionalen Arguments festlegt. Die `defaultArg` Funktion nimmt den optionalen Parameter als erstes Argument und der Standardwert als das zweite.

Das folgende Beispiel veranschaulicht die Verwendung von optionalen Parametern.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

Die Ausgabe lautet wie folgt.

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
```

## <a name="passing-by-reference"></a>Übergeben als Verweis
F# unterstützt die `byref` Schlüsselwort, das angibt, dass ein Parameter als Verweis übergeben wird. Dies bedeutet, dass alle Änderungen an den Wert nach der Ausführung der Funktion beibehalten werden. Werte bereitgestellt, um eine `byref` Parameter muss geändert werden. Alternativ können Sie Referenzzellen des entsprechenden Typs übergeben.

Übergeben als Verweis in .NET-Sprachen hat sich als eine Möglichkeit, mehr als einen Wert aus einer Funktion zurückgeben. In F# erläutert werden können Sie zu diesem Zweck ein Tupel zurückgeben oder eine änderbare Referenzzelle als Parameter verwenden. Die `byref` Parameter wird hauptsächlich für die Interoperabilität mit.

Die folgenden Beispiele veranschaulichen die Verwendung der `byref` Schlüsselwort. Beachten Sie, wenn Sie eine Referenzzelle als Parameter verwenden, muss eine Referenzzelle als einen benannten Wert erstellen und zu verwenden, die als Parameter nicht nur hinzufügen der `ref` Operator wie im ersten Aufruf von gezeigt `Increment` in den folgenden Code. Da eine Kopie des zugrunde liegenden Werts erstellen eine Referenzzelle erstellt wird, erhöht der erste Aufruf nur einen temporären Wert.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3809.fs)]

Sie können ein Tupel als Rückgabewert einer speichern `out` Parameter in .NET-Methoden-Bibliothek. Alternativ können Sie behandeln die `out` Parameter als ein `byref` Parameter. Im folgenden Codebeispiel wird veranschaulicht beide Möglichkeiten.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a>Parameterarrays
Gelegentlich ist es erforderlich, um eine Funktion definieren, die eine beliebige Anzahl von Parametern heterogenen Typs akzeptiert. Es wäre nicht praktikabel ist, erstellen alle möglichen überladenen Methoden um für alle Typen zu berücksichtigen, die verwendet werden können. Die .NET Implementierungen bieten Unterstützung für solche Methoden über die Parameter-Array-Funktion. Eine Methode, die in der Signatur ein Parameterarray akzeptiert, kann mit einer beliebigen Anzahl von Parametern angegeben werden. Die Parameter werden in ein Array eingefügt. Der Typ der Arrayelemente bestimmt die Parametertypen, die an die Funktion übergeben werden können. Wenn Sie das Parameterarray mit definieren `System.Object` als Elementtyps Clientcode kann Werte dann übergeben eines beliebigen Typs.

In f# können Parameterarrays nur in Methoden definiert werden. Sie können nicht verwendet werden, in der eigenständigen Funktionen oder Funktionen, die in Modulen definiert sind.

Definieren Sie ein Parameterarray mithilfe der `ParamArray` Attribut. Die `ParamArray` Attribut kann nur auf den letzten Parameter angewendet werden.

Das folgende Codebeispiel veranschaulicht eine .NET-Methode übergeben wird, die ein Parameterarray und die Definition eines Typs in f# verwendet, die eine Methode verfügt, die ein Parameterarray akzeptiert beide aufrufen.

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

Wenn in einem Projekt ausführen, lautet die Ausgabe des vorherigen Codes wie folgt:

```
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a>Siehe auch
[Mitglieder](members/index.md)
