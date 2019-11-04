---
title: Aktive Muster
description: Erfahren Sie, wie Sie mit aktiven Mustern benannte Partitionen definieren, die Eingabedaten in der F# Programmiersprache unterteilen.
ms.date: 05/16/2016
ms.openlocfilehash: f5ed4a8600cba10d23d01628aba6ca07e543c586
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425092"
---
# <a name="active-patterns"></a>Aktive Muster

Mit *aktiven Mustern* können Sie benannte Partitionen definieren, die Eingabedaten unterteilen, sodass Sie diese Namen wie bei einer Unterscheidungs-Union in einem Muster Vergleichs Ausdruck verwenden können. Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.

## <a name="syntax"></a>Syntax

```fsharp
// Active pattern of one choice.
let (|identifier|) [arguments] valueToMatch= expression

// Active Pattern with multiple choices.
// Uses a FSharp.Core.Choice<_,...,_> based on the number of case names. In F#, the limitation n <= 7 applies.
let (|identifer1|identifier2|...|) valueToMatch = expression

// Partial active pattern definition.
// Uses a FSharp.Core.option<_> to represent if the type is satisfied at the call site.
let (|identifier|_|) [arguments ] valueToMatch = expression
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax sind die Bezeichner Namen für Partitionen der Eingabedaten, die durch *Argumente*dargestellt werden, d. h. Namen für Teilmengen der Menge aller Werte der Argumente. Eine aktive Muster Definition kann bis zu sieben Partitionen aufweisen. Der *Ausdruck* beschreibt das Formular, in das die Daten zerlegt werden. Sie können eine aktive Muster Definition verwenden, um die Regeln zum Bestimmen der benannten Partitionen zu definieren, zu denen die als Argumente angegebenen Werte gehören. Die Symbole (| und |) werden als *Bananen Clips* bezeichnet, und die von dieser Art der Let-Bindung erstellte Funktion wird als *aktive Erkennung*bezeichnet.

Sehen Sie sich als Beispiel das folgende aktive Muster mit einem Argument an.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

Sie können das aktive Muster in einem Muster Vergleichs Ausdruck verwenden, wie im folgenden Beispiel gezeigt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

Die Ausgabe dieses Programms lautet wie folgt:

```console
7 is odd
11 is odd
32 is even
```

Eine andere Verwendung von aktiven Mustern besteht darin, Datentypen auf verschiedene Weise zu zerlegen, z. b. wenn die gleichen zugrunde liegenden Daten verschiedene mögliche Darstellungen haben. Beispielsweise kann ein `Color` Objekt in eine RGB-Darstellung oder eine HSB-Darstellung zerlegt werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

Die Ausgabe des obigen Programms lautet wie folgt:

```console
Red
 Red: 255 Green: 0 Blue: 0
 Hue: 360.000000 Saturation: 1.000000 Brightness: 0.500000
Black
 Red: 0 Green: 0 Blue: 0
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.000000
White
 Red: 255 Green: 255 Blue: 255
 Hue: 0.000000 Saturation: 0.000000 Brightness: 1.000000
Gray
 Red: 128 Green: 128 Blue: 128
 Hue: 0.000000 Saturation: 0.000000 Brightness: 0.501961
BlanchedAlmond
 Red: 255 Green: 235 Blue: 205
 Hue: 36.000000 Saturation: 1.000000 Brightness: 0.901961
```

In Kombination können Sie mit diesen beiden Methoden zum Verwenden von aktiven Mustern Daten in das entsprechende Formular partitionieren und Zerlegen sowie die entsprechenden Berechnungen für die entsprechenden Daten in der für die Berechnung am besten geeigneten Form ausführen.

Die sich ergebenden Muster Vergleichsausdrücke ermöglichen es, Daten auf bequeme Weise zu schreiben, die sehr lesbar ist, und potenziell komplexe Verzweigungen und Datenanalyse Code erheblich zu vereinfachen.

## <a name="partial-active-patterns"></a>Teilweise aktive Muster

Manchmal müssen Sie nur einen Teil des Eingabe Raums partitionieren. In diesem Fall schreiben Sie eine Reihe von partiellen Mustern, von denen jedes mit einigen Eingaben identisch ist, aber nicht mit anderen Eingaben verglichen werden kann. Aktive Muster, die nicht immer einen Wert ergeben, werden als *teilweise aktive Muster*bezeichnet. Sie verfügen über einen Rückgabewert, der ein Optionstyp ist. Wenn Sie ein teilweise aktives Muster definieren möchten, verwenden Sie ein Platzhalter Zeichen (\_) am Ende der Liste der Muster innerhalb der Bananen Clips. Der folgende Code veranschaulicht die Verwendung eines teilweise aktiven Musters.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

Die Ausgabe des vorherigen Beispiels lautet wie folgt:

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Wenn Sie teilweise aktive Muster verwenden, kann es vorkommen, dass die einzelnen Optionen zusammen hanglos oder sich gegenseitig ausschließen, aber nicht sein müssen. Im folgenden Beispiel sind das Muster Quadrat und der Pattern-Cube nicht zusammen hanglos, da einige Zahlen sowohl Quadrate als auch Cubes sind, z. b. 64. Im folgenden Programm werden das-Muster und das-Muster verwendet, um die Quadrat-und die Cube-Muster Dabei werden alle ganzen Zahlen bis zu 1000 gedruckt, bei denen es sich um Quadrate und Cubes handelt, sowie um diejenigen, bei denen es sich nur um Cubes handelt.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

Die Ausgabe lautet wie folgt:

```console
1 is a cube and a square
8 is a cube
27 is a cube
64 is a cube and a square
125 is a cube
216 is a cube
343 is a cube
512 is a cube
729 is a cube and a square
1000 is a cube
```

## <a name="parameterized-active-patterns"></a>Parametrisierte aktive Muster

Aktive Muster akzeptieren immer mindestens ein Argument für das Element, das abgeglichen wird, Sie können jedoch auch zusätzliche Argumente annehmen. in diesem Fall gilt das *parametrisierte aktive Muster* für den Namen. Mit zusätzlichen Argumenten kann ein allgemeines Muster spezialisiert werden. Beispielsweise enthalten aktive Muster, die reguläre Ausdrücke zum Analysieren von Zeichen folgen verwenden, häufig den regulären Ausdruck als zusätzlichen Parameter, wie im folgenden Code gezeigt, der auch das teilweise aktive Muster verwendet `Integer` das im vorherigen Codebeispiel definiert wurde. In diesem Beispiel werden Zeichen folgen, die reguläre Ausdrücke für verschiedene Datumsformate verwenden, angegeben, um das allgemeine allgemeine parametopx-Muster anzupassen. Das aktive integermuster wird verwendet, um die übereinstimmenden Zeichen folgen in ganze Zahlen zu konvertieren, die an den DateTime-Konstruktor übergeben werden können.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

Die Ausgabe des vorherigen Codes lautet wie folgt:

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

Aktive Muster sind nicht auf Muster Vergleichsausdrücke beschränkt, Sie können Sie auch bei let-Bindungen verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

Die Ausgabe des vorherigen Codes lautet wie folgt:

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Vergleichsausdrücke](match-expressions.md)
