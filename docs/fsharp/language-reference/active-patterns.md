---
title: Aktive Muster (F#)
description: Erfahren Sie, wie mit aktiven Mustern verwenden, um benannte Partitionen definieren, die Eingabedaten in der Programmiersprache f# zu unterteilen.
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: dotnet-fsharp
ms.devlang: fsharp
ms.openlocfilehash: 66e1e39c4822ec7262642d301ceb1deea17fcb8c
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2018
---
# <a name="active-patterns"></a>Aktive Muster

*Aktive Muster* ermöglichen es Ihnen, definieren benannte Partitionen, die Eingabedaten zu unterteilen, damit Sie diese Namen in einem Mustervergleichsausdruck wie für eine Unterscheidungs-Union verwenden können. Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.


## <a name="syntax"></a>Syntax

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a>Hinweise
In der vorherigen Syntax sind die Bezeichner Namen für Partitionen der Eingabedaten, die von dargestellte *Argumente*, oder in anderen Worten: die Namen für Teilmengen der Menge aller Werte der Argumente. Es kann bis zu sieben Partitionen in der Definition eines aktiven Musters vorhanden sein. Die *Ausdruck* beschreibt die Form, in der die Daten zerlegt werden sollen. Definition eines aktiven Musters können Sie definieren die Regeln zum bestimmen, welche benannten Partitionen die Werte, die als Argumente zu gehören. Der (| und |) Symbole werden als bezeichnet *Bananenklammern* und die Funktion erstellt, die von diesem Typ der Let-Bindung wird ein *aktive Erkennung*.

Beispielsweise sollten Sie die folgenden aktive Muster mit einem Argument.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

Sie können das aktive Muster in einem Mustervergleichsausdruck wie im folgenden Beispiel gezeigt verwenden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

Die Ausgabe dieses Programms lautet wie folgt:

```
7 is odd
11 is odd
32 is even
```

Eine weitere Verwendungsmöglichkeit der aktive Muster ist zum Zerlegen von Datentypen auf verschiedene Weise, wie z. B. wenn die gleichen zugrunde liegenden Daten verschiedene mögliche Darstellungen aufweist. Angenommen, ein `Color` Objekt konnte in eine RGB-Darstellung oder eine HSB-Darstellung zerlegt werden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

Die Ausgabe des oben genannten Programms lautet wie folgt:

```
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

In Kombination diese beiden Methoden mit aktiven Mustern ermöglichen Ihnen eine Partition Daten in der entsprechenden Format zerlegen und führen Sie die entsprechenden Berechnungen auf die entsprechenden Daten in der für die Berechnung am einfachsten Form.

Die resultierende Muster übereinstimmende Ausdrücke aktivieren Daten auf einfache Weise geschrieben werden, die schwer lesbar, erheblich vereinfachen potenziell komplexen Verzweigen und Datencode für die Analyse ist.


## <a name="partial-active-patterns"></a>Partielle aktive Muster
In einigen Fällen müssen Sie nur einen Teil der Eingabe Speicherplatz zu partitionieren. In diesem Fall schreiben Sie einen Satz von partiellen Mustern, von denen mit einigen Eingaben übereinstimmt, aber nicht andere Eingaben entsprechen. Aktive Muster, die immer keinen Wert zurückgibt, heißen *partielle aktive Muster*; sie haben einen Rückgabewert, der ein Optionstyp ist. Um eine partielle aktive Muster zu definieren, verwenden Sie ein Platzhalterzeichen (_) am Ende der Liste von Mustern innerhalb der Bananenklammern. Der folgende Code veranschaulicht die Verwendung eines partiellen aktiven Musters.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

Die Ausgabe des vorherigen Beispiels lautet wie folgt:

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Wenn Sie teilweise mit aktiven Mustern verwenden, können manchmal die einzelnen Optionen nicht zusammenhängenden oder sich gegenseitig ausschließende, jedoch müssen nicht sein. Im folgenden Beispiel sind die Muster Square und Cube-Muster nicht zusammenhanglos, da einige Zahlen Quadrate und Cubes, z. B. 64 darstellen. Das folgende Programm druckt alle ganzen Zahlen bis 1000000, die Quadrate und Cubes sind.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

Die Ausgabe lautet wie folgt:

```
1
64
729
4096
15625
46656
117649
262144
531441
1000000
```

## <a name="parameterized-active-patterns"></a>Parametrisierte aktive Muster
Aktive Muster akzeptieren immer mindestens ein Argument für das Element, das abgeglichen wird, aber möglicherweise nehmen sie weitere Argumente als auch in diesem Fall, dass der Name *parametrisierte aktives Muster* gilt. Mit zusätzlichen Argumenten kann es sich um ein allgemeines Muster spezialisiert werden. Aktive Muster, die Verwendung von regulären Ausdrücken zum Analysieren von Zeichenfolgen häufig umfassen z. B. den regulären Ausdruck als zusätzlichen Parameter, wie im folgenden Code, der auch das partielle aktive Muster verwendet `Integer` im vorherigen Codebeispiel definiert. In diesem Beispiel sind Zeichenfolgen, die regulären Ausdrücke für verschiedene Datumsformate verwenden angegeben, die allgemeine aktive Muster ParseRegex anpassen. Aktive Integer-Muster wird verwendet, die übereinstimmenden Zeichenfolgen in ganze Zahlen konvertiert, die an den DateTime-Konstruktor übergeben werden kann.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

Die Ausgabe des vorherigen Codes lautet wie folgt:

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

Aktive Muster sind nicht nur auf übereinstimmende Ausdrücke das Muster beschränkt, Sie können diese auch für Let-Bindungen verwenden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

Die Ausgabe des vorherigen Codes lautet wie folgt:

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Siehe auch
[F#-Sprachreferenz](index.md)

[Vergleichsausdrücke](match-expressions.md)

