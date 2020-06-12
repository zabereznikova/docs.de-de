---
title: Funktionen
description: Erfahren Sie mehr über Funktionen in F# und darüber, wie F# gängige Konstrukte für die funktionale Programmierung unterstützt.
ms.date: 05/16/2016
ms.openlocfilehash: e49183e0634dee1750757abadbfe9e9c824f51a8
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596473"
---
# <a name="functions"></a>Funktionen

Funktionen sind die grundlegende Einheit für die Ausführung des Programms in einer beliebigen Programmiersprache. So wie in anderen Sprachen auch, verfügt eine F#-Funktion über einen Namen, kann Parameter besitzen und Argumente verwenden und verfügt über Text. F# unterstützt auch funktionale Konstrukte der Programmierung, z.B. das Behandeln von Funktionen als Werte, Verwenden von unbenannten Funktionen als Ausdrücke, die Zusammensetzung von Funktionen zum Bilden neuer Funktionen, Funktionen mit Currying sowie die implizite Definition von Funktionen mit der teilweise Anwendung von Funktionsargumenten.

Sie definieren Funktionen durch Verwendung des Schlüsselworts `let` oder – sofern die Funktion rekursiv ist – die Schlüsselwortkombination `let rec`.

## <a name="syntax"></a>Syntax

```fsharp
// Non-recursive function definition.
let [inline] function-name parameter-list [ : return-type ] = function-body
// Recursive function definition.
let rec function-name parameter-list = recursive-function-body
```

## <a name="remarks"></a>Hinweise

Der *function-name* ist ein Bezeichner, der die Funktion darstellt. Der Bezeichner *parameter-list* besteht aus aufeinanderfolgenden Parametern, die durch Leerzeichen getrennt sind. Sie können einen expliziten Typ für jeden Parameter angeben, wie im Abschnitt „Parameter“ beschrieben. Wenn Sie keinen bestimmten Argumenttyp angeben, versucht der Compiler den Typ aus dem Funktionsrumpf abzuleiten. *function-body* besteht aus einem Ausdruck. Der Ausdruck, der den Funktionsrumpf bildet, ist in der Regel ein zusammengesetzter Ausdruck, bestehend aus einer Reihe von Ausdrücken, die in einem abschließenden Ausdruck enden, was der Rückgabewert ist. Der *return-type* ist ein Doppelpunkt, dem ein Typ folgt und der optional ist. Wenn Sie den Typ des Rückgabewerts nicht explizit angeben, bestimmt der Compiler den Rückgabetyp anhand des abschließenden Ausdrucks.

Eine einfache Funktionsdefinition lautet ungefähr folgendermaßen:

```fsharp
let f x = x + 1
```

Im vorherigen Beispiel ist der Funktionsname ist `f`, das Argument `x`, das den Typ `int` verweist, der Funktionsrumpf ist `x + 1`, und der Rückgabewert ist vom Typ `int`.

Funktionen können als `inline` markiert werden. Informationen zu `inline` finden Sie unter [Inlinefunktionen](inline-functions.md).

## <a name="scope"></a>Bereich

Auf jeder Ebene des Bereichs, der nicht der Modulbereich ist, ist es kein Fehler, einen Wert oder einen Namen einer Funktion Namen erneut zu verwenden. Wenn Sie einen Namen wiederverwenden, führt der später deklarierte Name zum Shadowing des früher deklarierten Namens. Im Bereich der obersten Ebene in einem Modul, müssen Namen jedoch eindeutig sein. Der folgende Code generiert z.B. einen Fehler, wenn er im Modulbereich erscheint, jedoch nicht, wenn er innerhalb einer Funktion angezeigt wird:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet101.fs)]

Der folgende Code ist jedoch auf jeder Ebene des Bereichs akzeptabel:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet102.fs)]

### <a name="parameters"></a>Parameter

Namen von Parametern werden nach dem Funktionsnamen aufgeführt. Sie können einen Typ für einen Parameter angeben, wie im folgenden Beispiel gezeigt:

```fsharp
let f (x : int) = x + 1
```

Wenn Sie einen Typ angeben, folgt er auf den Namen des Parameters und wird durch einen Doppelpunkt von diesem getrennt. Wenn Sie den Typ für den Parameter weglassen, wird der Parametertyp vom Compiler abgeleitet. In der folgenden Funktion wird z.B. das Argument `x` vom Typ `int` abgeleitet, da 1 vom Typ `int` ist.

```fsharp
let f x = x + 1
```

Allerdings versucht der Compiler die Funktion so allgemein wie möglich zu machen. Beachten Sie beispielsweise folgenden Code:

```fsharp
let f x = (x, x)
```

Die Funktion erstellt ein Tupel aus einem Argument eines beliebigen Typs. Da der Typ nicht angegeben ist, kann die Funktion mit jedem Argumenttyp verwendet werden. Weitere Informationen finden Sie unter [Automatische Verallgemeinerung](../generics/automatic-generalization.md).

## <a name="function-bodies"></a>Funktionsrümpfe

Ein Funktionsrumpf kann Definitionen von lokalen Variablen und Funktionen enthalten. Diese Variablen und Funktionen sind im Bereich des Texts der aktuellen Funktion enthalten, jedoch nicht außerhalb. Wenn Sie die einfache Syntaxoption aktiviert haben, müssen Sie einen Einzug verwenden, um anzugeben, dass sich eine Definition in einem Funktionsrumpf befindet, so wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet103.fs)]

Weitere Informationen finden Sie unter [Richtlinien für das Formatieren von Code](../../style-guide/formatting.md) und [Ausführliche Syntax](../verbose-syntax.md).

## <a name="return-values"></a>Rückgabewerte

Der Compiler verwendet den letzten Ausdruck in einem Funktionsrumpf, um den Rückgabewert und den Typ zu bestimmen. Der Compiler kann den Typ des abschließenden Ausdrucks möglicherweise von vorherigen Ausdrücken ableiten. In der Funktion `cylinderVolume`, die im vorherigen Abschnitt gezeigt wird, wird bestimmt, dass der Typ `pi` vom Typ des Literals `3.14159``float` ist. Der Compiler verwendet den Typ `pi`, um zu bestimmen, dass der Typ des Ausdrucks `h * pi * r * r``float` ist. Daher ist der allgemeine Rückgabetyp der Funktion `float`.

Um den Rückgabewert explizit anzugeben, schreiben Sie den Code wie folgt:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet105.fs)]

Wie der oben geschriebene Code, wendet der Compiler **float** auf gesamten Funktion an; wenn Sie sie auch auf Parametertypen anwenden möchten, verwenden Sie folgenden Code:

```fsharp
let cylinderVolume (radius : float) (length : float) : float
```

## <a name="calling-a-function"></a>Aufrufen einer Funktion

Sie können Funktionen aufrufen, indem den Funktionsnamen, gefolgt von einem Leerzeichen angeben, und dann beliebige Argumente, die durch Leerzeichen getrennt sind. Um z.B. die Funktion **cylinderVolume** abzurufen und das Ergebnis dem Wert **vol** zuzuweisen, schreiben Sie folgenden Code:

```fsharp
let vol = cylinderVolume 2.0 3.0
```

## <a name="partial-application-of-arguments"></a>Teilweise Anwendung von Argumenten

Wenn Sie weniger als die angegebene Anzahl von Argumenten angeben, erstellen Sie eine neue Funktion, die die übrigen Argumente erwartet. Diese Methode zum Behandeln von Argumenten  wird als *Currying* bezeichnet und ist ein Merkmal funktionaler Programmiersprachen wie F#. Nehmen wir beispielsweise an, dass Sie mit zwei Pipegrößen arbeiten: eine besitzt den Radius von **2,0** und die andere einen Radius von **3,0**. Sie können Funktionen erstellen, die die Menge der Pipe wie folgt bestimmen:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet106.fs)]

Sie geben dann das zusätzliche Argument an, das für unterschiedliche Längen der Pipe mit den zwei verschiedenen Größen benötigt wird:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet107.fs)]

## <a name="recursive-functions"></a>Rekursive Funktionen

*Rekursive Funktionen* sind Funktionen, die sich selbst aufrufen. Sie erfordern die Angabe des Schlüsselworts **rec**, das dem Schlüsselwort **let** folgt. Rufen Sie die rekursive Funktion im Rumpf der Funktion so auf, wie Sie auch jede andere Funktion aufrufen würden. Die folgende rekursive Funktion berechnet die *n.* Fibonacci-Zahl. Die die Fibonacci-Zahlenfolge ist seit dem Altertum bekannt und ist eine Sequenz, in der die einzelnen aufeinander folgenden Zahlen die Summe der vorherigen zwei Zahlen in der Sequenz sind.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet108.fs)]

Einige rekursive Funktionen können auf einem Programmstapel möglicherweise zum Überlauf führen oder ineffizient ausgeführt werden, wenn Sie sie nicht sorgfältig und unter Beachtung besonderer Methoden schreiben, z.B. mit der Verwendung von Akkumulatoren und Fortsetzungen.

## <a name="function-values"></a>Funktionswerte

In F# werden alle Funktionen als Werte betrachtet. Sie sind in der Tat als *Funktionswerte* bekannt. Da Funktionen Werte sind, können sie als Argumente für andere Funktionen oder in anderen Kontexten verwendet werden, in denen Werte verwendet werden. Es folgt ein Beispiel für eine Funktion, die den Wert einer Funktion als Argument akzeptiert:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet109.fs)]

Sie geben den Typ eines Funktionswerts mithilfe des `->`-Token an. Auf der linken Seite dieses Tokens befindet sich der Typ des Arguments, und auf der rechten Seite befindet sich der Rückgabewert. Im vorherigen Beispiel ist `apply1` eine Funktion, die eine `transform`-Funktion als Argument verwendet, wobei `transform` eine Funktion ist, die einen Integer nimmt und einen anderen dafür zurückgibt. Im folgenden Code wird die Verwendung von `apply1` veranschaulicht:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet110.fs)]

Der Wert von `result` wird nach der Ausführung des vorangehenden Codes 101 sein.

Mehrere Argumente werden durch aufeinander folgende `->`-Token getrennt, wie im folgenden Beispiel gezeigt:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet111.fs)]

Das Ergebnis ist 200.

## <a name="lambda-expressions"></a>Lambda-Ausdrücke

Ein *Lambdaausdruck* ist eine unbenannte Funktion. Im vorherigen Beispiel könnten Sie Lambdaausdrücke verwenden, anstatt benannte Funktionen als **increment** und **mul** zu definieren.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet112.fs)]

Sie definieren Lambdaausdrücke mithilfe des `fun`-Schlüsselworts. Ein Lambdaausdruck ähnelt einer Funktionsdefinition, außer dass statt eines `=`-Tokens das `->`-Token zum Trennen der Argumentliste vom Funktionsrumpf verwendet wird. So wie in einer regulären Funktionsdefinition, können Argumenttypen explizit abgeleitet oder angegeben werden. Der Rückgabetyp des Lambdaausdrucks wird vom Typ des letzten Ausdrucks im Text abgeleitet. Weitere Informationen finden Sie unter [Lambdaausdrücke: Das Schlüsselwort `fun`](lambda-expressions-the-fun-keyword.md).

## <a name="function-composition-and-pipelining"></a>Funktionskomposition und Pipelining

Funktionen in F# können aus anderen Funktionen zusammengestellt werden. Die Zusammensetzung der beiden Funktionen **function1** und **function2** ist eine weitere Funktion, die die Anwendung von **function1** gefolgt von der Anwendung von **function2** darstellt:

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet113.fs)]

Das Ergebnis ist 202.

Pipelining ermöglicht, dass Funktionsaufrufe miteinander als aufeinanderfolgende Operationen verkettet werden. Pipelining funktioniert wie Folgt:

```fsharp
let result = 100 |> function1 |> function2
```

Das Ergebnis ist wieder 202.

Die Kompositionsoperatoren nehmen zwei Funktionen und geben eine Funktion zurück. Dagegen nehmen Pipeline-Operatoren eine Funktion und ein Argument und geben einen Wert zurück. Das folgende Codebeispiel zeigt den Unterschied zwischen den Pipeline- und Kompositionsoperatoren durch Darstellung der Unterschiede in den Funktionssignaturen und in der Nutzung.

```fsharp
// Function composition and pipeline operators compared.

let addOne x = x + 1
let timesTwo x = 2 * x

// Composition operator
// ( >> ) : ('T1 -> 'T2) -> ('T2 -> 'T3) -> 'T1 -> 'T3
let Compose2 = addOne >> timesTwo

// Backward composition operator
// ( << ) : ('T2 -> 'T3) -> ('T1 -> 'T2) -> 'T1 -> 'T3
let Compose1 = addOne << timesTwo

// Result is 5
let result1 = Compose1 2

// Result is 6
let result2 = Compose2 2

// Pipelining
// Pipeline operator
// ( |> ) : 'T1 -> ('T1 -> 'U) -> 'U
let Pipeline2 x = addOne x |> timesTwo

// Backward pipeline operator
// ( <| ) : ('T -> 'U) -> 'T -> 'U
let Pipeline1 x = addOne <| timesTwo x

// Result is 5
let result3 = Pipeline1 2

// Result is 6
let result4 = Pipeline2 2
```

## <a name="overloading-functions"></a>Überladen von Funktionen

Sie können die Methoden eines Typs überladen, jedoch keine Funktionen. Weitere Informationen finden Sie unter [Methoden](../members/methods.md).

## <a name="see-also"></a>Siehe auch

- [Werte](../values/index.md)
- [F#-Sprachreferenz](../index.md)
