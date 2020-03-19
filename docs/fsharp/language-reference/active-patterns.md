---
title: Aktive Muster
description: Erfahren Sie, wie Sie mithilfe aktiver Muster benannte Partitionen definieren, die Eingabedaten in der Programmiersprache F- unterteilen.
ms.date: 05/16/2016
ms.openlocfilehash: 898ef201369683bfd49d53e863e86f919f5837fe
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79187057"
---
# <a name="active-patterns"></a>Aktive Muster

*Mit aktiven Mustern* können Sie benannte Partitionen definieren, die Eingabedaten unterteilen, sodass Sie diese Namen in einem Musterabgleichsausdruck genauso verwenden können wie für eine diskriminierte Union. Mit aktiven Mustern können Sie Daten benutzerdefiniert für jede Partition zerlegen.

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

## <a name="remarks"></a>Bemerkungen

In der vorherigen Syntax sind die Bezeichner Namen für Partitionen der Eingabedaten, die durch *Argumente*dargestellt werden, oder, mit anderen Worten, Namen für Teilmengen des Satzes aller Werte der Argumente. Es können bis zu sieben Partitionen in einer aktiven Musterdefinition vorhanden sein. Der *Ausdruck* beschreibt die Form, in die die Daten zerlegen werden sollen. Sie können eine aktive Musterdefinition verwenden, um die Regeln zum Bestimmen zu definieren, zu welcher der benannten Partitionen die als Argumente angegebenen Werte gehören. Die Symbole (| und |) werden als *Bananenclips* bezeichnet, und die Funktion, die von diesem Typ der let-Bindung erstellt wird, wird als *aktive Erkennung*bezeichnet.

Betrachten Sie als Beispiel das folgende aktive Muster mit einem Argument.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5001.fs)]

Sie können das aktive Muster in einem Musterabgleichsausdruck verwenden, wie im folgenden Beispiel.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5002.fs)]

Die Ausgabe dieses Programms ist wie folgt:

```console
7 is odd
11 is odd
32 is even
```

Eine weitere Verwendung von aktiven Mustern besteht darin, Datentypen auf verschiedene Arten zu zerlegen, z. B. wenn dieselben zugrunde liegenden Daten verschiedene mögliche Darstellungen aufweisen. Beispielsweise kann `Color` ein Objekt in eine RGB-Darstellung oder eine HSB-Darstellung zerlegt werden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5003.fs)]

Die Ausgabe des obigen Programms ist wie folgt:

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

In Kombination mit diesen beiden Methoden der Verwendung aktiver Muster können Sie Daten in die entsprechende Form partitionieren und zersetzen und die entsprechenden Berechnungen für die entsprechenden Daten in der für die Berechnung am besten geeigneten Daten durchführen.

Die resultierenden Musterabgleichsausdrücke ermöglichen das Schreiben von Daten auf eine bequeme, sehr lesbare Weise, was potenziell komplexen Verzweigungs- und Datenanalysecode erheblich vereinfacht.

## <a name="partial-active-patterns"></a>Teilweise aktive Muster

Manchmal müssen Sie nur einen Teil des Eingabebereichs partitionieren. In diesem Fall schreiben Sie einen Satz von Teilmustern, die jeweils mit einigen Eingaben übereinstimmen, aber nicht mit anderen Eingaben übereinstimmen. Aktive Muster, die nicht immer einen Wert erzeugen, werden als *partielle aktive Muster*bezeichnet. Sie haben einen Rückgabewert, der ein Optionstyp ist. Um ein partielles aktives Muster\_zu definieren, verwenden Sie ein Platzhalterzeichen ( ) am Ende der Liste der Muster innerhalb der Bananenclips. Der folgende Code veranschaulicht die Verwendung eines partiellen aktiven Musters.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5004.fs)]

Die Ausgabe des vorherigen Beispiels ist wie folgt:

```console
1.100000 : Floating point
0 : Integer
0.000000 : Floating point
10 : Integer
Something else : Not matched.
```

Bei der Verwendung partieller aktiver Muster können die einzelnen Entscheidungen manchmal getrennt oder sich gegenseitig ausschließen, aber sie müssen es nicht sein. Im folgenden Beispiel sind das Muster Quadrat und der Musterwürfel nicht getrennt, da einige Zahlen sowohl Quadrate als auch Würfel sind, z. B. 64. Das folgende Programm verwendet das UND-Muster, um die Quadrat- und Würfelmuster zu kombinieren. Es druckt alle ganzen Zahlen bis zu 1000 aus, die sowohl Quadrate und Würfel sind, als auch solche, die nur Würfel sind.

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

Aktive Muster verwenden immer mindestens ein Argument für das übereinstimmende Element, aber sie können auch zusätzliche Argumente annehmen, in diesem Fall gilt das *namensparametrierte aktive Muster.* Zusätzliche Argumente ermöglichen es, ein allgemeines Muster zu spezialisieren. Aktive Muster, die reguläre Ausdrücke zum Analysieren von Zeichenfolgen verwenden, enthalten beispielsweise häufig den regulären Ausdruck `Integer` als zusätzlichen Parameter, wie im folgenden Code, der auch das im vorherigen Codebeispiel definierte partielle aktive Muster verwendet. In diesem Beispiel werden Zeichenfolgen, die reguläre Ausdrücke für verschiedene Datumsformate verwenden, angegeben, um das allgemeine aktive ParseRegex-Muster anzupassen. Das aktive Ganzzahlmuster wird verwendet, um die übereinstimmenden Zeichenfolgen in ganze Zahlen zu konvertieren, die an den DateTime-Konstruktor übergeben werden können.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5006.fs)]

Die Ausgabe des vorherigen Codes ist wie folgt:

```console
12/22/2008 12:00:00 AM 1/1/2009 12:00:00 AM 1/15/2008 12:00:00 AM 12/28/1995 12:00:00 AM
```

Aktive Muster sind nicht nur auf Musterabgleichsausdrücke beschränkt, sondern können sie auch für Let-Bindings verwenden.

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5007.fs)]

Die Ausgabe des vorherigen Codes ist wie folgt:

```console
Hello, random citizen!
Hello, George!
```

## <a name="see-also"></a>Weitere Informationen

- [Sprachreferenz](index.md)
- [Vergleichsausdrücke](match-expressions.md)
