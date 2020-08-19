---
title: Arrays
description: 'Erfahren Sie, wie Sie Arrays in der Programmiersprache F # erstellen und verwenden.'
ms.date: 08/13/2020
ms.openlocfilehash: 93d524046ff93a7f1b04e72d580d9d0e1360ba0b
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558880"
---
# <a name="arrays"></a>Arrays

Arrays sind nullbasierte, änderbare Sequenzen fester Größe von aufeinander folgenden Datenelementen, die alle den gleichen Typ aufweisen.

## <a name="create-arrays"></a>Erstellen von Arrays

Sie können Arrays auf verschiedene Arten erstellen. Sie können ein kleines Array erstellen, indem Sie aufeinander folgende Werte zwischen `[|` und `|]` und durch Semikolons getrennt auflisten, wie in den folgenden Beispielen gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

Sie können auch jedes Element in einer eigenen Zeile anordnen. In diesem Fall ist das Semikolontrennzeichen optional.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

Der Typ der Arrayelemente wird von den verwendeten Literalen abgeleitet, und er muss konsistent sein. Somit verursacht der folgende Code einen Fehler, da 1.0 ein Gleitkommawert ist und 2 und 3 ganze Zahlen sind.

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

Sie können Arrays mithilfe von Sequenzausdrücken erstellen. Im folgenden Beispiel wird ein Array aus den Quadraten von ganzen Zahlen zwischen 1 und 10 erstellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

Verwenden Sie `Array.zeroCreate`, um ein Array zu erstellen, dessen sämtliche Elemente mit 0 (null) initialisiert sind.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="access-elements"></a>Zugriffs Elemente

Sie können auf Array Elemente zugreifen, indem Sie einen Punkt Operator ( `.` ) und eckige Klammern ( `[` und `]` ) verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

Array Indizes beginnen bei 0.

Der Zugriff auf Arrayelemente kann auch mit Slicenotation erfolgen, die es Ihnen ermöglicht, einen Teilbereich des Arrays anzugeben. Im Folgenden erhalten Sie Beispiele für Slicenotation.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

Bei Verwendung von Slicenotation wird eine neue Kopie des Arrays erstellt.

## <a name="array-types-and-modules"></a>Array Typen und-Module

Alle F#-Arrays sind vom .NET Framework-Typ <xref:System.Array?displayProperty=nameWithType>. Daher unterstützen F#-Arrays alle in <xref:System.Array?displayProperty=nameWithType> verfügbaren Funktionen.

Das [ `Array` Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) unterstützt Vorgänge für eindimensionale Arrays. Die Module `Array2D`, `Array3D` und `Array4D` enthalten Funktionen, die Operationen für Arrays mit zwei, drei bzw. vier Dimensionen unterstützen. Mit <xref:System.Array?displayProperty=nameWithType> können Sie Arrays mit einem Rang größer vier erstellen.

### <a name="simple-functions"></a>Einfache Funktionen

[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) Ruft ein Element ab. [`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) Gibt die Länge eines Arrays an. [`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) legt ein Element auf einen angegebenen Wert fest. Im folgenden Codebeispiel wird die Verwendung dieser Funktionen veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

Die Ausgabe lautet wie folgt.

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a>Funktionen zum Erstellen von Arrays

Mehrere Funktionen erstellen Arrays, ohne ein vorhandenes Array zu erfordern. [`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) erstellt ein neues Array, das keine-Elemente enthält. [`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) erstellt ein Array mit einer angegebenen Größe und legt alle Elemente auf bereitgestellte Werte fest. [`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) erstellt ein Array, wobei eine Dimension und eine Funktion zum Generieren der Elemente angegeben werden. [`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) erstellt ein Array, in dem alle Elemente mit dem Nullwert für den Typ des Arrays initialisiert werden. Dieser Code demonstriert die Funktionen.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

Die Ausgabe lautet wie folgt.

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) erstellt ein neues Array, das Elemente enthält, die aus einem vorhandenen Array kopiert werden. Beachten Sie, dass die Kopie eine flache Kopie ist, d. h., wenn der Elementtyp ein Verweistyp ist, wird nur der Verweis, nicht das zugrunde liegende Objekt kopiert. Dies wird im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

Der obige Code gibt Folgendes aus:

```console
[|Test1; Test2; |]
[|; Test2; |]
```

Die Zeichenfolge `Test1` wird nur im ersten Array angezeigt, da der Vorgang der Erstellung eines neuen Elements, den Verweis in `firstArray` überschreibt, aber sich nicht auf den ursprünglichen Verweis auf eine leere Zeichenfolge auswirkt, die immer noch im `secondArray` vorhanden ist. Die Zeichenfolge `Test2` wird in beiden Arrays angezeigt, da sich die `Insert`-Operation für den <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Typ auf das zugrundeliegende <xref:System.Text.StringBuilder?displayProperty=nameWithType>-Objekt auswirkt, auf das in beiden Arrays verwiesen wird.

[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) generiert ein neues Array aus einem Teilbereich eines Arrays. Sie geben den Teilbereich an, indem Sie den Startindex und die Länge bereitstellen. Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.sub`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

Die Ausgabe zeigt an, dass das Unterfeld bei Element "5" beginnt und 10 Elemente enthält.

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) erstellt ein neues Array, indem zwei vorhandene Arrays kombiniert werden.

Der folgende Code veranschaulicht **Array. Append**.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```console
[|1; 2; 3; 4; 5; 6|]
```

[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) wählt Elemente eines Arrays aus, die in ein neues Array eingeschlossen werden sollen. Der folgende Code stellt `Array.choose` dar. Beachten Sie, dass der Elementtyp des Arrays nicht zum Typ des Werts passen muss, der im Optionstyp zurückgegeben wurde. In diesem Beispiel ist der Elementtyp `int`, und die Option ist das Ergebnis einer Polynomfunktion (`elem*elem - 1`) als Gleitkommazahl.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) führt eine angegebene Funktion für jedes Array Element eines vorhandenen Arrays aus und sammelt dann die von der Funktion generierten Elemente und kombiniert Sie in einem neuen Array. Der folgende Code stellt `Array.collect` dar.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) nimmt eine Sequenz von Arrays an und kombiniert Sie zu einem einzelnen Array. Der folgende Code stellt `Array.concat` dar.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) nimmt eine boolesche Bedingungs Funktion an und generiert ein neues Array, das nur die Elemente aus dem Eingabe Array enthält, für die die Bedingung true ist. Der folgende Code stellt `Array.filter` dar.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```console
[|2; 4; 6; 8; 10|]
```

[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) generiert ein neues Array, indem die Reihenfolge eines vorhandenen Arrays umgekehrt wird. Der folgende Code stellt `Array.rev` dar.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```console
"Hello world!"
```

Sie können Funktionen im Array Modul, die Arrays transformieren, mit dem Pipeline Operator () problemlos kombinieren `|>` , wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

Ausgabe:

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a>Mehrdimensionale Arrays

Ein mehrdimensionales Array kann erstellt werden, jedoch gibt es keine Syntax zum Schreiben eines mehrdimensionalen Arrayliterals. Verwenden Sie den-Operator [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) , um ein Array aus einer Sequenz von Sequenzen von Array Elementen zu erstellen. Die Sequenzen können Array- oder Listenliterale sein. Im folgenden Code wird z. B. ein zweidimensionales Array erstellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

Sie können auch die-Funktion verwenden, [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) um Arrays von zwei Dimensionen zu initialisieren, und ähnliche Funktionen sind für Arrays mit drei und vier Dimensionen verfügbar. Diese Funktionen nehmen eine Funktion, die zum Erstellen der Elemente verwendet wird. Zum Erstellen eines zweidimensionalen Arrays, das Elemente enthält, die auf einen Anfangswert festgelegt sind, anstatt eine Funktion anzugeben, verwenden Sie die- [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) Funktion, die auch für Arrays mit bis zu vier Dimensionen verfügbar ist. Im folgenden Codebeispiel wird die Erstellung eines Arrays von Arrays mit den gewünschten Elementen veranschaulicht, und dann wird mit `Array2D.init` das gewünschte zweidimensionale Array generiert.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

Arrayindizierung und das Aufteilen von Syntax in Slices werden für Arrays bis zu Rang 4 unterstützt. Wenn Sie einen Index in mehreren Dimensionen angeben, verwenden Sie Kommas, um die Indizes zu trennen, wie im folgenden Codebeispiel veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

Der Typ eines zweidimensionalen Arrays wird als `<type>[,]` (z. B.,`int[,]`, `double[,]`) geschrieben, und der Typ eines dreidimensionalen Arrays wird als `<type>[,,]` usw. für Arrays mit mehr Dimensionen geschrieben.

Nur eine Teilmenge der Funktionen für eindimensionale Arrays ist auch für mehrdimensionale Arrays verfügbar.

### <a name="array-slicing-and-multidimensional-arrays"></a>Array-aufteilen und mehrdimensionale Arrays

In einem zweidimensionalen Array (eine Matrix) können Sie eine untergeordnete Matrix extrahieren, indem Sie Bereiche angeben und ein Platzhalter `*` Zeichen () verwenden, um ganze Zeilen oder Spalten anzugeben.

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

Sie können ein mehrdimensionales Array in unter Elemente derselben oder einer niedrigeren Dimension zerlegen. Beispielsweise können Sie einen Vektor aus einer Matrix abrufen, indem Sie eine einzelne Zeile oder eine Spalte angeben.

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

Sie können diese segmentierende Syntax für Typen verwenden, die die Elementzugriffsoperatoren und die überladenen `GetSlice`-Methoden implementieren. Beispielsweise erstellt der folgende Code einen Matrixtyp, der das F# 2D-Array umschließt, eine Elementeigenschaft implementiert, um Unterstützung für die Arrayindizierung bereitzustellen, und drei Versionen von `GetSlice` implementiert. Wenn Sie diesen Code als Vorlage für Ihre Matrixtypen verwenden können, können Sie alle in diesem Abschnitt beschriebenen Segmentierungsvorgänge verwenden.

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a>Boolesche Funktionen für Arrays

Die Funktionen [`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) und [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) Testelemente in jeweils einem oder zwei Arrays. Diese Funktionen akzeptieren eine Testfunktion und geben `true` zurück, wenn die Bedingung von einem Element (oder Elementpaaren für `Array.exists2`) erfüllt wird.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.exists` und `Array.exists2`. In diesen Beispielen werden neue Funktionen durch das Übernehmen von nur einem der Argumente, in diesen Fällen das Funktionsargument, erstellt.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

Die Ausgabe des vorhergehenden Codes entspricht dem Folgenden.

```console
true
false
false
true
```

Ebenso testet die-Funktion [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) ein Array, um zu bestimmen, ob jedes Element eine boolesche Bedingung erfüllt. Die Variation [`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2) führt dasselbe aus, indem eine boolesche Funktion verwendet wird, die Elemente von zwei Arrays gleicher Länge einbezieht. Im folgenden Code wird die Verwendung dieser Funktionen veranschaulicht.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

Die Ausgabe dieser Beispiele lautet folgendermaßen.

```console
false
true
true
false
```

### <a name="search-arrays"></a>Arrays suchen

[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) nimmt eine boolesche Funktion an und gibt das erste Element zurück, für das die Funktion zurückgibt `true` , oder löst eine aus, <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> Wenn kein Element gefunden wird, das die Bedingung erfüllt. [`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) ist wie `Array.find` , mit der Ausnahme, dass Sie den Index des-Elements anstelle des-Elements selbst zurückgibt.

Der folgende Code sucht mithilfe von `Array.find` und `Array.findIndex` eine Zahl, die sowohl ein perfektes Quadrat als auch perfekter Cube ist.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

Die Ausgabe lautet wie folgt.

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) ist wie `Array.find` , mit der Ausnahme, dass das Ergebnis ein Optionstyp ist, und gibt zurück, `None` Wenn kein Element gefunden wird. `Array.tryFind` sollte statt `Array.find` verwendet werden, wenn nicht bekannt ist, ob ein entsprechendes Element im Array vorhanden ist. Ebenso verhält [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) sich wie, `Array.findIndex` mit der Ausnahme, dass der Optionstyp der Rückgabewert ist. Wenn kein Element gefunden wird, lautet die Option `None`.

Das folgende Codebeispiel veranschaulicht die Verwendung von `Array.tryFind`. Dieser Code hängt vom vorherigen Code ab.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

Die Ausgabe lautet wie folgt.

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

Verwenden [`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick) Sie, wenn Sie ein Element zusätzlich zu dessen Suche transformieren müssen. Das Ergebnis ist das erste Element, für das die Funktion das transformierte Element als Optionswert zurückgibt, oder `None`, wenn kein solches Element gefunden wird.

Im folgenden Code wird die Verwendung von `Array.tryPick` veranschaulicht: In diesem Fall werden statt eines Lambdaausdrucks mehrere lokale Hilfsfunktionen definiert, um den Code zu vereinfachen.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

Die Ausgabe lautet wie folgt.

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="perform-computations-on-arrays"></a>Ausführen von Berechnungen für Arrays

Die- [`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average) Funktion gibt den Durchschnitt der einzelnen Elemente in einem Array zurück. Sie ist auf Elementtypen beschränkt, die die exakte Division durch eine ganze Zahl unterstützen, wozu Gleitkommatypen aber keine ganzzahligen Typen gehören. Die- [`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy) Funktion gibt den Durchschnitt der Ergebnisse zurück, die durch den Aufruf einer Funktion für jedes Element verursacht werden. Für ein Array eines ganzzahligen Typs können Sie `Array.averageBy` verwenden und für die Berechnung die Funktion jedes Element in einen Gleitkommatyp konvertieren lassen.

Verwenden [`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) Sie oder, um das maximale oder minimale Element zu erhalten, wenn der Elementtyp es unterstützt. Ebenso wie [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) und [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) ermöglichen, dass eine Funktion zuerst ausgeführt wird, vielleicht zum Transformieren in einen Typ, der den Vergleich unterstützt.

[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) Fügt die Elemente eines Arrays hinzu und [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) Ruft für jedes Element eine Funktion auf und addiert die Ergebnisse.

Verwenden Sie, um eine Funktion für jedes Element in einem Array auszuführen, ohne die Rückgabewerte zu speichern [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter) . Verwenden Sie für eine Funktion mit zwei Arrays gleicher Länge [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2) . Wenn Sie auch ein Array der Ergebnisse der Funktion beibehalten müssen, verwenden Sie [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) oder [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2) , das jeweils zwei Arrays verwendet.

Die Variationen [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) und [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) ermöglichen, dass der Index des Elements an der Berechnung beteiligt ist. das gleiche gilt für [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) und [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2) .

Die Funktionen [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold) , [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack) , [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce) , [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack) , [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan) und [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) führen Algorithmen aus, die alle Elemente eines Arrays einbeziehen. Ebenso werden die Variationen [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) und [`Array.foldBack2`](foldBack2) Berechnungen für zwei Arrays durchgeführt.

Diese Funktionen zum Ausführen von Berechnungen entsprechen den Funktionen desselben Namens im [Listen Modul](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html). Verwendungs Beispiele finden Sie unter [Listen](lists.md).

### <a name="modify-arrays"></a>Arrays ändern

[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) legt ein Element auf einen angegebenen Wert fest. [`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) legt einen Bereich von Elementen in einem Array auf einen angegebenen Wert fest. Das folgende Codebeispiel enthält ein Beispiel für `Array.fill`.

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

Die Ausgabe lautet wie folgt.

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

Sie können verwenden [`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit) , um einen unter Abschnitt eines Arrays in ein anderes Array zu kopieren.

### <a name="convert-to-and-from-other-types"></a>Konvertieren in und aus anderen Typen

[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) erstellt ein Array aus einer Liste. [`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) erstellt ein Array aus einer Sequenz. [`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) und [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) Konvertieren in diese anderen Auflistungs Typen aus dem Arraytyp.

### <a name="sort-arrays"></a>Arrays sortieren

Verwenden [`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort) Sie, um ein Array mithilfe der generischen Vergleichsfunktion zu sortieren. Verwenden [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) Sie, um eine Funktion anzugeben, die einen Wert generiert, der als *Schlüssel*bezeichnet wird, um mithilfe der generischen Vergleichsfunktion für den Schlüssel zu sortieren. Verwenden [`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith) Sie, wenn Sie eine benutzerdefinierte Vergleichsfunktion bereitstellen möchten. `Array.sort`, `Array.sortBy` und `Array.sortWith` geben das sortierte Array als neues Array zurück. Die Variationen [`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace) , [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy) und [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) ändern das vorhandene Array, anstatt ein neues Array zurückzugeben.

### <a name="arrays-and-tuples"></a>Arrays und Tupel

Die Funktionen [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) und [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) konvertieren Arrays von tupelpaaren in Tupel von Arrays und umgekehrt. [`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) und [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) sind ähnlich, mit dem Unterschied, dass Sie mit Tupeln von drei Elementen oder Tupeln von drei Arrays funktionieren.

## <a name="parallel-computations-on-arrays"></a>Parallele Berechnungen von Arrays

Das-Modul [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) enthält Funktionen zum Ausführen paralleler Berechnungen für Arrays. Dieses Modul ist in Anwendungen nicht verfügbar, die auf Versionen vor Version 4 von .NET Framework abzielen.

## <a name="see-also"></a>Weitere Informationen

- [F#-Sprachreferenz](index.md)
- [F#-Typen](fsharp-types.md)
