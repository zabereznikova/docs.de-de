---
title: Aktive Muster
description: Erfahren Sie, wie aktive Muster zu verwenden, um benannte Partitionen definieren, die Eingabedaten in der Programmiersprache F# zu unterteilen.
ms.date: 05/16/2016
ms.openlocfilehash: 0f1f57de425836738201d2d8f84ab67a0df142ee
ms.sourcegitcommit: 3630c2515809e6f4b7dbb697a3354efec105a5cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2019
ms.locfileid: "58412083"
---
# <a name="active-patterns"></a>Aktive Muster

*Aktive Muster* ermöglichen es Ihnen, definieren benannte Partitionen, die Eingabedaten unterteilen, sodass Sie diese Namen in einem musterabgleichsausdruck wie für eine Unterscheidungs-Union verwenden können. Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.

## <a name="syntax"></a>Syntax

```fsharp
// Complete active pattern definition.
let (|identifer1|identifier2|...|) [ arguments ] = expression
// Partial active pattern definition.
let (|identifier|_|) [ arguments ] = expression
```

## <a name="remarks"></a>Hinweise

In der vorherigen Syntax wird der Bezeichner sind die Namen für die Partitionen der Eingabedaten, die durch dargestellt werden *Argumente*, oder in anderen Worten: die Namen für Teilmengen der Menge aller Werte der Argumente. Es können bis zu sieben Partitionen in der Definition eines aktiven Musters vorhanden sein. Die *Ausdruck* beschreibt die Form, in dem die Daten zu zerlegen. Definition eines aktiven Musters können Sie definieren die Regeln zur Bestimmung der benannte Partitionen die Werte, die als Argumente zu gehören. Die (| und |) Symbole werden als bezeichnet *Bananenklammern* und die Funktion, die von diesem Typ der Let-Bindung erstellt haben, heißt ein *aktive Erkennung*.

Betrachten Sie beispielsweise das folgende aktive Muster mit einem Argument aus.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

Sie können das aktive Muster in einem musterabgleichsausdruck wie im folgenden Beispiel gezeigt verwenden.

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

Die Ausgabe dieses Programms lautet wie folgt aus:

```
7 is odd
11 is odd
32 is even
```

Eine weitere Verwendungsmöglichkeit der aktive Muster ist Zerlegen von Datentypen auf verschiedene Weise, wie z. B. wenn die gleichen zugrunde liegenden Daten mögliche Darstellungen aufweist. Z. B. eine `Color` Objekt in eine RGB-Darstellung oder eine HSB-Darstellung zerlegt werden kann.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

Die Ausgabe des obigen Programms lautet wie folgt aus:

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

In Kombination mit aktiven Mustern diese beiden Methoden ermöglichen Ihnen die Partition Daten in nur das entsprechende Formular zu zerlegen und führen Sie die entsprechenden Berechnungen für die entsprechenden Daten in der Form, die am einfachsten, für die Berechnung.

Die resultierende mustervergleichsausdrücke ermöglichen, Daten auf einfache Weise geschrieben werden, die sehr gut lesbar, erheblich vereinfachen potenziell komplexen Branchen und Datencode für die Analyse ist.

## <a name="partial-active-patterns"></a>Partielle aktive Muster

In einigen Fällen müssen Sie nur einen Teil der Eingabe Speicherplatz zu partitionieren. In diesem Fall schreiben Sie eine Gruppe von partiellen Mustern, von denen einige Eingaben überein, aber nicht andere Eingaben entsprechen. Aktive Muster, die keine immer einen Wert produzieren heißen *partielle aktive Muster*; sie haben einen Rückgabewert, der ein Optionstyp ist. Um eine partielle aktive Muster zu definieren, verwenden Sie ein Platzhalterzeichen (\_) am Ende der Liste der Muster innerhalb der Bananenklammern. Der folgende Code veranschaulicht die Verwendung von partiellen aktiven Musters.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

Die Ausgabe des vorherigen Beispiels lautet wie folgt aus:

```
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Wenn Sie partielle aktive Muster zu verwenden, können manchmal die einzelnen Optionen zusammenhanglosen oder sich gegenseitig ausschließende, jedoch keine sein müssen. Im folgenden Beispiel sind das Muster Quadrat und den Cube-Muster nicht zusammenhanglos, da einige Zahlen sowohl Quadrate und Cubes, z. B. 64 sind. Das folgende Programm verwendet die AND-Muster, das Quadrat und den Cube-Muster kombiniert. Drucken alle ganzen Zahlen bis zu 1000, die sowohl Quadrate und Cubes, als auch diejenigen, bei die nur auf Cubes sind. 

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5005.fs)]

Die Ausgabe lautet wie folgt:

```
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

Aktive Muster akzeptieren immer mindestens ein Argument für das Element, das abgeglichen wird, aber unter Umständen akzeptieren sie zusätzliche Argumente ebenfalls in diesem Fall, dass der Name *parametrisiertes aktives Muster* gilt. Mit zusätzlichen Argumenten kann es sich um ein allgemeines Muster spezialisiert werden. Aktive Muster, mit denen reguläre Ausdrücke zum Analysieren von Zeichenfolgen häufig kann beispielsweise den regulären Ausdruck als zusätzlichen Parameter, wie im folgenden Code, der auch das partielle aktive Muster verwendet `Integer` im vorherigen Codebeispiel definiert. In diesem Beispiel werden Zeichenfolgen, die reguläre Ausdrücke für verschiedene Datumsformate verwenden angegeben, um das allgemeine ParseRegex-aktiv-Muster anzupassen. Ganzzahl aktiven Musters wird verwendet, die übereinstimmenden Zeichenfolgen in ganze Zahlen zu konvertieren, die an den DateTime-Konstruktor übergeben werden kann.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

Die Ausgabe des vorherigen Codes lautet wie folgt aus:

```
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

Aktive Muster sind nicht nur für Muster übereinstimmende Ausdrücke beschränkt, Sie können sie auch in Let-Bindungen verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

Die Ausgabe des vorherigen Codes lautet wie folgt aus:

```
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Siehe auch

- [F#-Sprachreferenz](index.md)
- [Vergleichsausdrücke](match-expressions.md)
